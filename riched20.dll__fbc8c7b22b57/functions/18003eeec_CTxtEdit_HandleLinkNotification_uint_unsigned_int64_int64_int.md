# CTxtEdit::HandleLinkNotification(uint,unsigned __int64,__int64,int *)

- ea: `0x18003eeec`
- end: `0x18003f113`
- name: `?HandleLinkNotification@CTxtEdit@@QEAAHI_K_JPEAH@Z`
- size: `551`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180027b20`
- `0x18005ee7c`
- `0x18005f078`
- `0x18005f424`

## callees

- `0x18002c58c`
- `0x18002c5d8`
- `0x18002dce0`
- `0x18003eeec`
- `0x180041200`
- `0x18004ae60`
- `0x180095010`

## import_xrefs

- `USER32!GetCursorPos` at `0x18003ef60`
- `USER32!GetCursorPos` at `0x18003ef60`

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
0x18003eeec  push    rbp
0x18003eeee  push    rbx
0x18003eeef  push    rsi
0x18003eef0  push    rdi
0x18003eef1  push    r14
0x18003eef3  push    r15
0x18003eef5  lea     rbp, [rsp-18h]
0x18003eefa  sub     rsp, 118h
0x18003ef01  mov     rdi, [rbp+40h+arg_20]
0x18003ef05  mov     rsi, r9
0x18003ef08  mov     r15, r8
0x18003ef0b  mov     r14d, edx
0x18003ef0e  mov     rbx, rcx
0x18003ef11  test    rdi, rdi
0x18003ef14  jz      short loc_18003EF1C
0x18003ef16  mov     dword ptr [rdi], 0
0x18003ef1c  test    dword ptr [rcx+0B0h], 4000000h
0x18003ef26  jz      loc_18003F100
0x18003ef2c  test    byte ptr [rcx+0B4h], 8
0x18003ef33  jz      loc_18003F100
0x18003ef39  movzx   eax, si
0x18003ef3c  mov     [rsp+140h+Point.x], eax
0x18003ef40  mov     rax, rsi
0x18003ef43  shr     rax, 10h
0x18003ef47  movzx   eax, ax
0x18003ef4a  mov     [rsp+140h+Point.y], eax
0x18003ef4e  mov     dword ptr [rbp+40h+arg_20], 0
0x18003ef55  cmp     r14d, 20h ; ' '
0x18003ef59  jnz     short loc_18003EF8C
0x18003ef5b  lea     rcx, [rsp+140h+Point]; lpPoint
0x18003ef60  call    cs:__imp_GetCursorPos
0x18003ef67  nop     dword ptr [rax+rax+00h]
0x18003ef6c  mov     rcx, [rbx+30h]
0x18003ef70  lea     rdx, [rsp+140h+Point]
0x18003ef75  mov     rax, [rcx]
0x18003ef78  mov     rax, [rax+0A0h]
0x18003ef7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef84  test    eax, eax
0x18003ef86  jz      loc_18003F100
0x18003ef8c  mov     rcx, [rbx+40h]
0x18003ef90  lea     rdx, [rbp+40h+arg_20]
0x18003ef94  mov     [rsp+140h+var_100], 0
0x18003ef9d  xor     r9d, r9d
0x18003efa0  mov     [rsp+140h+var_108], 0
0x18003efa9  xor     r8d, r8d
0x18003efac  mov     [rsp+140h+var_110], rdx
0x18003efb1  mov     rax, [rcx]
0x18003efb4  mov     rdx, qword ptr [rsp+140h+Point.x]
0x18003efb9  mov     dword ptr [rsp+140h+var_118], 0
0x18003efc1  mov     [rsp+140h+var_120], 0
0x18003efca  mov     rax, [rax+0E8h]
0x18003efd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efd6  cmp     dword ptr [rbp+40h+arg_20], 7
0x18003efda  jnz     loc_18003F100
0x18003efe0  xorps   xmm0, xmm0
0x18003efe3  mov     [rbp+40h+arg_0], 0
0x18003efea  xor     ecx, ecx
0x18003efec  mov     [rsp+140h+var_F0], 0
0x18003eff4  mov     [rbp+40h+var_B0], ecx
0x18003eff7  xor     r9d, r9d; int
0x18003effa  lea     rcx, [rbp+40h+var_A0]; this
0x18003effe  mov     r8d, eax; int
0x18003f001  mov     rdx, rbx; struct CTxtEdit *
0x18003f004  movups  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003f009  movups  [rsp+140h+var_D0], xmm0
0x18003f00e  movups  [rbp+40h+var_C0], xmm0
0x18003f012  call    ??0CTxtRange@@QEAA@PEAVCTxtEdit@@JJ@Z; CTxtRange::CTxtRange(CTxtEdit *,long,long)
0x18003f017  xorps   xmm0, xmm0
0x18003f01a  xor     eax, eax
0x18003f01c  test    dword ptr [rbx+0B4h], 8000000h
0x18003f026  movups  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003f02b  mov     [rbp+40h+var_B0], eax
0x18003f02e  movups  [rsp+140h+var_D0], xmm0
0x18003f033  movups  [rbp+40h+var_C0], xmm0
0x18003f037  jz      short loc_18003F068
0x18003f039  lea     rcx, [rbx+10h]
0x18003f03d  mov     rax, [rcx]
0x18003f040  lea     rdx, [rsp+140h+var_E0]
0x18003f045  mov     rax, [rax+130h]
0x18003f04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f051  mov     rcx, [rsp+140h+var_E0]; HWND
0x18003f056  mov     edx, 0FFFFFFF4h; int
0x18003f05b  call    ?GetWindowLong@CW32System@@SAJPEAUHWND__@@H@Z; CW32System::GetWindowLong(HWND__ *,int)
0x18003f060  movsxd  rcx, eax
0x18003f063  mov     [rsp+140h+var_E0+8], rcx
0x18003f068  mov     dword ptr [rsp+140h+var_D0], 70Bh
0x18003f070  test    rdi, rdi
0x18003f073  jz      short loc_18003F07B
0x18003f075  mov     dword ptr [rdi], 1
0x18003f07b  xor     r9d, r9d; int *
0x18003f07e  lea     rax, [rsp+140h+var_F0]
0x18003f083  mov     [rsp+140h+var_118], rax; int *
0x18003f088  lea     rcx, [rbp+40h+var_A0]; this
0x18003f08c  lea     rax, [rbp+40h+arg_0]
0x18003f090  mov     edx, 80000020h; int
0x18003f095  mov     [rsp+140h+var_120], rax; int *
0x18003f09a  lea     r8d, [r9+1]; int
0x18003f09e  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x18003f0a3  mov     edx, [rbp+40h+arg_0]; int
0x18003f0a6  mov     rcx, rbx; this
0x18003f0a9  mov     dword ptr [rsp+140h+var_D0+8], r14d
0x18003f0ae  mov     qword ptr [rsp+140h+var_D0+0Ch], r15
0x18003f0b3  mov     qword ptr [rbp+40h+var_C0+4], rsi
0x18003f0b7  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18003f0bc  mov     edx, [rsp+140h+var_F0]; int
0x18003f0c0  mov     rcx, rbx; this
0x18003f0c3  mov     dword ptr [rbp+40h+var_C0+0Ch], eax
0x18003f0c6  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18003f0cb  mov     rcx, [rbx+30h]
0x18003f0cf  lea     r8, [rsp+140h+var_E0]
0x18003f0d4  mov     [rbp+40h+var_B0], eax
0x18003f0d7  mov     edx, 70Bh
0x18003f0dc  mov     rax, [rcx]
0x18003f0df  mov     rax, [rax+130h]
0x18003f0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0eb  xor     ebx, ebx
0x18003f0ed  lea     rcx, [rbp+40h+var_A0]; this
0x18003f0f1  cmp     eax, 1
0x18003f0f4  setz    bl
0x18003f0f7  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18003f0fc  mov     eax, ebx
0x18003f0fe  jmp     short loc_18003F102
0x18003f100  xor     eax, eax
0x18003f102  add     rsp, 118h
0x18003f109  pop     r15
0x18003f10b  pop     r14
0x18003f10d  pop     rdi
0x18003f10e  pop     rsi
0x18003f10f  pop     rbx
0x18003f110  pop     rbp
0x18003f111  retn
```
