# CTxtEdit::HandleLinkNotification(uint,unsigned __int64,__int64,int *)

- ea: `0x18003e2d4`
- end: `0x18003e4f4`
- name: `?HandleLinkNotification@CTxtEdit@@QEAAHI_K_JPEAH@Z`
- size: `544`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18002cfd0`
- `0x18005d798`
- `0x18005d98c`
- `0x18005dd30`

## callees

- `0x180031974`
- `0x1800319c0`
- `0x180033060`
- `0x18003e2d4`
- `0x1800404ac`
- `0x180049cf4`
- `0x180092010`

## import_xrefs

- `USER32!GetCursorPos` at `0x18003e348`
- `USER32!GetCursorPos` at `0x18003e348`

## pseudocode

```c
_BOOL8 __fastcall CTxtEdit::HandleLinkNotification(CTxtEdit *this, int a2, __int64 a3, __int64 a4, int *a5)
{
  int *v5; // rdi
  int v10; // eax
  bool v11; // zf
  int v12; // r8d
  int v13; // r8d
  int AcpFromCp; // eax
  __int64 v15; // rcx
  BOOL v16; // ebx
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  struct tagPOINT Point; // [rsp+58h] [rbp-A8h] BYREF
  HWND v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v21[2]; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+90h] [rbp-70h]
  _BYTE v23[160]; // [rsp+A0h] [rbp-60h] BYREF
  int v24; // [rsp+150h] [rbp+50h] BYREF

  v5 = a5;
  if ( a5 )
    *a5 = 0;
  if ( (*((_DWORD *)this + 44) & 0x4000000) == 0 )
    return 0;
  if ( (*((_BYTE *)this + 180) & 8) == 0 )
    return 0;
  Point.x = (unsigned __int16)a4;
  Point.y = WORD1(a4);
  LODWORD(a5) = 0;
  if ( a2 == 32 )
  {
    GetCursorPos(&Point);
    if ( !(*(unsigned int (__fastcall **)(_QWORD, struct tagPOINT *))(**((_QWORD **)this + 6) + 160LL))(
            *((_QWORD *)this + 6),
            &Point) )
      return 0;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, struct tagPOINT, _QWORD, _QWORD, _QWORD, _DWORD, int **, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 232LL))(
          *((_QWORD *)this + 8),
          Point,
          0,
          0,
          0,
          0,
          &a5,
          0,
          0);
  if ( (_DWORD)a5 != 7 )
    return 0;
  v24 = 0;
  v18 = 0;
  v22 = 0;
  *(_OWORD *)v20 = 0;
  memset(v21, 0, sizeof(v21));
  CTxtRange::CTxtRange((CTxtRange *)v23, this, v10, 0);
  v11 = (*((_DWORD *)this + 45) & 0x8000000) == 0;
  *(_OWORD *)v20 = 0;
  v22 = 0;
  memset(v21, 0, sizeof(v21));
  if ( !v11 )
  {
    (*(void (__fastcall **)(char *, HWND *))(*((_QWORD *)this + 2) + 304LL))((char *)this + 16, v20);
    v20[1] = (HWND)(int)CW32System::GetWindowLong(v20[0], -12);
  }
  LODWORD(v21[0]) = 1803;
  if ( v5 )
    *v5 = 1;
  CTxtRange::Expander((CTxtRange *)v23, -2147483616, 1, 0, &v24, &v18);
  DWORD2(v21[0]) = a2;
  *(_QWORD *)((char *)v21 + 12) = a3;
  *(_QWORD *)((char *)&v21[1] + 4) = a4;
  HIDWORD(v21[1]) = CTxtEdit::GetAcpFromCp(this, v24, v12);
  AcpFromCp = CTxtEdit::GetAcpFromCp(this, v18, v13);
  v15 = *((_QWORD *)this + 6);
  v22 = AcpFromCp;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, HWND *))(*(_QWORD *)v15 + 304LL))(v15, 1803, v20) == 1;
  CTxtRange::~CTxtRange((CTxtRange *)v23);
  return v16;
}

```

## disassembly

```asm
0x18003e2d4  push    rbp
0x18003e2d6  push    rbx
0x18003e2d7  push    rsi
0x18003e2d8  push    rdi
0x18003e2d9  push    r14
0x18003e2db  push    r15
0x18003e2dd  lea     rbp, [rsp-18h]
0x18003e2e2  sub     rsp, 118h
0x18003e2e9  mov     rdi, [rbp+40h+arg_20]
0x18003e2ed  mov     rsi, r9
0x18003e2f0  mov     r15, r8
0x18003e2f3  mov     r14d, edx
0x18003e2f6  mov     rbx, rcx
0x18003e2f9  test    rdi, rdi
0x18003e2fc  jz      short loc_18003E304
0x18003e2fe  mov     dword ptr [rdi], 0
0x18003e304  test    dword ptr [rcx+0B0h], 4000000h
0x18003e30e  jz      loc_18003E4E2
0x18003e314  test    byte ptr [rcx+0B4h], 8
0x18003e31b  jz      loc_18003E4E2
0x18003e321  movzx   eax, si
0x18003e324  mov     [rsp+140h+Point.x], eax
0x18003e328  mov     rax, rsi
0x18003e32b  shr     rax, 10h
0x18003e32f  movzx   eax, ax
0x18003e332  mov     [rsp+140h+Point.y], eax
0x18003e336  mov     dword ptr [rbp+40h+arg_20], 0
0x18003e33d  cmp     r14d, 20h ; ' '
0x18003e341  jnz     short loc_18003E36E
0x18003e343  lea     rcx, [rsp+140h+Point]; lpPoint
0x18003e348  call    cs:__imp_GetCursorPos
0x18003e34e  mov     rcx, [rbx+30h]
0x18003e352  lea     rdx, [rsp+140h+Point]
0x18003e357  mov     rax, [rcx]
0x18003e35a  mov     rax, [rax+0A0h]
0x18003e361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e366  test    eax, eax
0x18003e368  jz      loc_18003E4E2
0x18003e36e  mov     rcx, [rbx+40h]
0x18003e372  lea     rdx, [rbp+40h+arg_20]
0x18003e376  mov     [rsp+140h+var_100], 0
0x18003e37f  xor     r9d, r9d
0x18003e382  mov     [rsp+140h+var_108], 0
0x18003e38b  xor     r8d, r8d
0x18003e38e  mov     [rsp+140h+var_110], rdx
0x18003e393  mov     rax, [rcx]
0x18003e396  mov     rdx, qword ptr [rsp+140h+Point.x]
0x18003e39b  mov     dword ptr [rsp+140h+var_118], 0
0x18003e3a3  mov     [rsp+140h+var_120], 0
0x18003e3ac  mov     rax, [rax+0E8h]
0x18003e3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3b8  cmp     dword ptr [rbp+40h+arg_20], 7
0x18003e3bc  jnz     loc_18003E4E2
0x18003e3c2  xorps   xmm0, xmm0
0x18003e3c5  mov     [rbp+40h+arg_0], 0
0x18003e3cc  xor     ecx, ecx
0x18003e3ce  mov     [rsp+140h+var_F0], 0
0x18003e3d6  mov     [rbp+40h+var_B0], ecx
0x18003e3d9  xor     r9d, r9d; int
0x18003e3dc  lea     rcx, [rbp+40h+var_A0]; this
0x18003e3e0  mov     r8d, eax; int
0x18003e3e3  mov     rdx, rbx; struct CTxtEdit *
0x18003e3e6  movups  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003e3eb  movups  [rsp+140h+var_D0], xmm0
0x18003e3f0  movups  [rbp+40h+var_C0], xmm0
0x18003e3f4  call    ??0CTxtRange@@QEAA@PEAVCTxtEdit@@JJ@Z; CTxtRange::CTxtRange(CTxtEdit *,long,long)
0x18003e3f9  xorps   xmm0, xmm0
0x18003e3fc  xor     eax, eax
0x18003e3fe  test    dword ptr [rbx+0B4h], 8000000h
0x18003e408  movups  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003e40d  mov     [rbp+40h+var_B0], eax
0x18003e410  movups  [rsp+140h+var_D0], xmm0
0x18003e415  movups  [rbp+40h+var_C0], xmm0
0x18003e419  jz      short loc_18003E44A
0x18003e41b  lea     rcx, [rbx+10h]
0x18003e41f  mov     rax, [rcx]
0x18003e422  lea     rdx, [rsp+140h+var_E0]
0x18003e427  mov     rax, [rax+130h]
0x18003e42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e433  mov     rcx, [rsp+140h+var_E0]; HWND
0x18003e438  mov     edx, 0FFFFFFF4h; int
0x18003e43d  call    ?GetWindowLong@CW32System@@SAJPEAUHWND__@@H@Z; CW32System::GetWindowLong(HWND__ *,int)
0x18003e442  movsxd  rcx, eax
0x18003e445  mov     [rsp+140h+var_E0+8], rcx
0x18003e44a  mov     dword ptr [rsp+140h+var_D0], 70Bh
0x18003e452  test    rdi, rdi
0x18003e455  jz      short loc_18003E45D
0x18003e457  mov     dword ptr [rdi], 1
0x18003e45d  xor     r9d, r9d; int *
0x18003e460  lea     rax, [rsp+140h+var_F0]
0x18003e465  mov     [rsp+140h+var_118], rax; int *
0x18003e46a  lea     rcx, [rbp+40h+var_A0]; this
0x18003e46e  lea     rax, [rbp+40h+arg_0]
0x18003e472  mov     edx, 80000020h; int
0x18003e477  mov     [rsp+140h+var_120], rax; int *
0x18003e47c  lea     r8d, [r9+1]; int
0x18003e480  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x18003e485  mov     edx, [rbp+40h+arg_0]; int
0x18003e488  mov     rcx, rbx; this
0x18003e48b  mov     dword ptr [rsp+140h+var_D0+8], r14d
0x18003e490  mov     qword ptr [rsp+140h+var_D0+0Ch], r15
0x18003e495  mov     qword ptr [rbp+40h+var_C0+4], rsi
0x18003e499  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18003e49e  mov     edx, [rsp+140h+var_F0]; int
0x18003e4a2  mov     rcx, rbx; this
0x18003e4a5  mov     dword ptr [rbp+40h+var_C0+0Ch], eax
0x18003e4a8  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18003e4ad  mov     rcx, [rbx+30h]
0x18003e4b1  lea     r8, [rsp+140h+var_E0]
0x18003e4b6  mov     [rbp+40h+var_B0], eax
0x18003e4b9  mov     edx, 70Bh
0x18003e4be  mov     rax, [rcx]
0x18003e4c1  mov     rax, [rax+130h]
0x18003e4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4cd  xor     ebx, ebx
0x18003e4cf  lea     rcx, [rbp+40h+var_A0]; this
0x18003e4d3  cmp     eax, 1
0x18003e4d6  setz    bl
0x18003e4d9  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18003e4de  mov     eax, ebx
0x18003e4e0  jmp     short loc_18003E4E4
0x18003e4e2  xor     eax, eax
0x18003e4e4  add     rsp, 118h
0x18003e4eb  pop     r15
0x18003e4ed  pop     r14
0x18003e4ef  pop     rdi
0x18003e4f0  pop     rsi
0x18003e4f1  pop     rbx
0x18003e4f2  pop     rbp
0x18003e4f3  retn
```
