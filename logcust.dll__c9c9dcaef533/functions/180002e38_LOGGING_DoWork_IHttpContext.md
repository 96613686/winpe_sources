# LOGGING::DoWork(IHttpContext *)

- ea: `0x180002e38`
- end: `0x180003058`
- name: `?DoWork@LOGGING@@QEAAXPEAVIHttpContext@@@Z`
- size: `544`
- prototype: `void __fastcall(LOGGING *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002378`

## callees

- `0x180002e38`
- `0x180003796`
- `0x1800037d0`
- `0x180004010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x180003003`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003023`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003003`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003023`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180002f9d`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180002f9d`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180002f33`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180002f33`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002f05`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002f05`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000302e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000302e`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002ed7`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002ed7`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180002eee`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180002eee`

## pseudocode

```c
void __fastcall LOGGING::DoWork(LOGGING *this, struct IHttpContext *a2)
{
  __int64 v4; // rax
  const char *v5; // rbx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 *v9; // rsi
  unsigned int v10; // edx
  __int64 v11; // rax
  _WORD v12[8]; // [rsp+20h] [rbp-E0h] BYREF
  void **v13; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v14[4]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+60h] [rbp-A0h]
  __int16 v17; // [rsp+64h] [rbp-9Ch]
  unsigned int v18; // [rsp+68h] [rbp-98h]
  struct IHttpContext *v19; // [rsp+70h] [rbp-90h]
  _BYTE v20[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v21[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-30h]
  char v23[128]; // [rsp+F0h] [rbp-10h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 112LL))(v4, 13);
    v14[0] = 0;
    v13 = &CInetLogInformation::`vftable';
    v16 = 32;
    v15 = v14;
    v17 = 256;
    v18 = 0;
    v19 = a2;
    STRA::STRA((STRA *)v20);
    if ( **((_BYTE **)this + 7) )
    {
      v5 = MULTISZA::First((LOGGING *)((char *)this + 24));
      STRA::STRA((STRA *)v21, v23, 0x80u);
      v12[0] = 0;
      if ( v5 )
      {
        while ( 1 )
        {
          v6 = -1;
          do
            ++v6;
          while ( v5[v6] );
          if ( (int)STRA::Copy((STRA *)v21, v5, v6 - 1) < 0 )
            break;
          v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, _WORD *))(*(_QWORD *)v7 + 24LL))(v7, v22, v12);
          v9 = (__int64 *)v8;
          if ( v8 )
          {
            LOWORD(v8) = v12[0];
          }
          else
          {
            v9 = &qword_180005FA8;
            v12[0] = 0;
          }
          if ( !BUFFER::Resize((BUFFER *)v14, (unsigned __int16)v8 + v18 + 2, 0x100u) )
            break;
          memcpy_0((char *)v15 + v18, v9, (unsigned int)v12[0] + 1);
          v10 = v18 + 1 + v12[0];
          v18 = v10;
          v11 = -1;
          do
            ++v11;
          while ( v5[v11] );
          v5 += v11 + 1;
          if ( !*v5 )
            goto LABEL_16;
        }
      }
      else
      {
        v10 = v18;
LABEL_16:
        *((_BYTE *)v15 + v10) = 0;
      }
      STRA::~STRA((STRA *)v21);
    }
    (*(void (__fastcall **)(_QWORD, void ***))(**((_QWORD **)this + 2) + 40LL))(*((_QWORD *)this + 2), &v13);
    STRA::~STRA((STRA *)v20);
    BUFFER::~BUFFER((BUFFER *)v14);
  }
}

```

## disassembly

```asm
0x180002e38  mov     [rsp-8+arg_10], rbx
0x180002e3d  mov     [rsp-8+arg_18], rsi
0x180002e42  push    rbp
0x180002e43  push    rdi
0x180002e44  push    r14
0x180002e46  lea     rbp, [rsp-80h]
0x180002e4b  sub     rsp, 180h
0x180002e52  mov     rax, cs:__security_cookie
0x180002e59  xor     rax, rsp
0x180002e5c  mov     [rbp+90h+var_20], rax
0x180002e60  cmp     qword ptr [rcx+10h], 0
0x180002e65  mov     r14, rdx
0x180002e68  mov     rdi, rcx
0x180002e6b  jz      loc_180003034
0x180002e71  mov     rax, [rdx]
0x180002e74  mov     rcx, rdx
0x180002e77  mov     rax, [rax+20h]
0x180002e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e80  mov     r8, rax
0x180002e83  mov     edx, 0Dh
0x180002e88  mov     rcx, [rax]
0x180002e8b  mov     rax, [rcx+70h]
0x180002e8f  mov     rcx, r8
0x180002e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e97  lea     rax, ??_7CInetLogInformation@@6B@; const CInetLogInformation::`vftable'
0x180002e9e  mov     [rsp+190h+var_158], 0
0x180002ea7  mov     [rsp+190h+var_160], rax
0x180002eac  lea     rcx, [rsp+190h+var_118]
0x180002eb1  lea     rax, [rsp+190h+var_158]
0x180002eb6  mov     [rsp+190h+var_130], 20h ; ' '
0x180002ebe  mov     [rsp+190h+var_138], rax
0x180002ec3  mov     [rsp+190h+var_12C], 100h
0x180002eca  mov     [rsp+190h+var_128], 0
0x180002ed2  mov     [rsp+190h+var_120], r14
0x180002ed7  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002edd  lea     rcx, [rdi+18h]
0x180002ee1  mov     rax, [rcx+20h]
0x180002ee5  cmp     byte ptr [rax], 0
0x180002ee8  jz      loc_180003009
0x180002eee  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x180002ef4  mov     r8d, 80h
0x180002efa  lea     rdx, [rbp+90h+var_A0]
0x180002efe  lea     rcx, [rbp+90h+var_E0]
0x180002f02  mov     rbx, rax
0x180002f05  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002f0b  xor     ecx, ecx
0x180002f0d  mov     [rsp+190h+var_170], cx
0x180002f12  test    rbx, rbx
0x180002f15  jz      loc_180002FF0
0x180002f1b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002f1f  inc     r8
0x180002f22  cmp     byte ptr [rbx+r8], 0
0x180002f27  jnz     short loc_180002F1F
0x180002f29  dec     r8d
0x180002f2c  lea     rcx, [rbp+90h+var_E0]
0x180002f30  mov     rdx, rbx
0x180002f33  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180002f39  test    eax, eax
0x180002f3b  js      loc_180002FFF
0x180002f41  mov     rax, [r14]
0x180002f44  mov     rcx, r14
0x180002f47  mov     rax, [rax+18h]
0x180002f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f50  mov     rdx, [rbp+90h+var_C0]
0x180002f54  lea     r8, [rsp+190h+var_170]
0x180002f59  mov     r9, rax
0x180002f5c  mov     rcx, [rax]
0x180002f5f  mov     rax, [rcx+18h]
0x180002f63  mov     rcx, r9
0x180002f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6b  mov     rsi, rax
0x180002f6e  test    rax, rax
0x180002f71  jnz     short loc_180002F81
0x180002f73  lea     rsi, qword_180005FA8
0x180002f7a  mov     [rsp+190h+var_170], ax
0x180002f7f  jmp     short loc_180002F86
0x180002f81  movzx   eax, [rsp+190h+var_170]
0x180002f86  mov     edx, [rsp+190h+var_128]
0x180002f8a  mov     r8d, 100h
0x180002f90  movzx   ecx, ax
0x180002f93  add     edx, 2
0x180002f96  add     edx, ecx
0x180002f98  lea     rcx, [rsp+190h+var_158]
0x180002f9d  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180002fa3  test    al, al
0x180002fa5  jz      short loc_180002FFF
0x180002fa7  movzx   r8d, [rsp+190h+var_170]
0x180002fad  mov     rdx, rsi; Src
0x180002fb0  mov     ecx, [rsp+190h+var_128]
0x180002fb4  inc     r8d; Size
0x180002fb7  add     rcx, [rsp+190h+var_138]; void *
0x180002fbc  call    memcpy_0
0x180002fc1  mov     eax, [rsp+190h+var_128]
0x180002fc5  movzx   edx, [rsp+190h+var_170]
0x180002fca  inc     eax
0x180002fcc  add     edx, eax
0x180002fce  mov     [rsp+190h+var_128], edx
0x180002fd2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002fd6  inc     rax
0x180002fd9  cmp     byte ptr [rbx+rax], 0
0x180002fdd  jnz     short loc_180002FD6
0x180002fdf  inc     rbx
0x180002fe2  add     rbx, rax
0x180002fe5  cmp     byte ptr [rbx], 0
0x180002fe8  jnz     loc_180002F1B
0x180002fee  jmp     short loc_180002FF4
0x180002ff0  mov     edx, [rsp+190h+var_128]
0x180002ff4  mov     rax, [rsp+190h+var_138]
0x180002ff9  mov     ecx, edx
0x180002ffb  mov     byte ptr [rcx+rax], 0
0x180002fff  lea     rcx, [rbp+90h+var_E0]
0x180003003  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003009  mov     rcx, [rdi+10h]
0x18000300d  lea     rdx, [rsp+190h+var_160]
0x180003012  mov     rax, [rcx]
0x180003015  mov     rax, [rax+28h]
0x180003019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301e  lea     rcx, [rsp+190h+var_118]
0x180003023  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003029  lea     rcx, [rsp+190h+var_158]
0x18000302e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003034  mov     rcx, [rbp+90h+var_20]
0x180003038  xor     rcx, rsp; StackCookie
0x18000303b  call    __security_check_cookie
0x180003040  lea     r11, [rsp+190h+var_10]
0x180003048  mov     rbx, [r11+30h]
0x18000304c  mov     rsi, [r11+38h]
0x180003050  mov     rsp, r11
0x180003053  pop     r14
0x180003055  pop     rdi
0x180003056  pop     rbp
0x180003057  retn
```
