# DpRegion::ValidateAndSetSlow(tagRECT const *,int)

- ea: `0x18013cf28`
- end: `0x18013d07e`
- name: `?ValidateAndSetSlow@DpRegion@@IEAA?AW4Status@@PEBUtagRECT@@H@Z`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18013cb9c`

## callees

- `0x18001f504`
- `0x180022450`
- `0x18008392c`
- `0x180084de8`
- `0x1800964f8`
- `0x1800e9380`
- `0x18013c960`
- `0x18013cf28`

## import_xrefs

- `ntdll!RtlLogUnexpectedCodepath` at `0x18013cf73`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18013d067`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18013cf73`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18013d067`

## pseudocode

```c
__int64 __fastcall DpRegion::ValidateAndSetSlow(_DWORD *a1, __int64 a2, int a3)
{
  int v6; // ebx
  int *v7; // rdi
  int v8; // eax
  int v9; // edx
  int v10; // r9d
  int v11; // r8d
  unsigned int v12; // esi
  int v14; // [rsp+30h] [rbp-39h] BYREF
  int v15; // [rsp+34h] [rbp-35h]
  __int64 v16; // [rsp+48h] [rbp-21h]
  int v17; // [rsp+50h] [rbp-19h]
  _BYTE v18[40]; // [rsp+58h] [rbp-11h] BYREF
  int v19; // [rsp+80h] [rbp+17h] BYREF
  int v20; // [rsp+84h] [rbp+1Bh]
  int v21; // [rsp+88h] [rbp+1Fh]

  v21 = 0;
  v19 = 56110386;
  v20 = 2;
  RtlLogUnexpectedCodepath(&v19);
  DpRegion::DpRegion((DpRegion *)v18, 1);
  v6 = 0;
  if ( a3 > 0 )
  {
    v7 = (int *)(a2 + 4);
    do
    {
      if ( (unsigned int)IsRectValid(a2 + 16LL * v6) )
      {
        v8 = v7[2] - *v7;
        v9 = *(v7 - 1);
        v10 = v7[1] - v9;
        v11 = *v7;
        v16 = 0;
        v15 &= ~4u;
        v17 = 0;
        v14 = 1733452849;
        DpRegion::Set((DpRegion *)&v14, v9, v11, v10, v8);
        v12 = DpRegion::Or(v18, &v14);
        if ( v12 )
        {
          v21 = 0;
          v19 = 56110386;
          v20 = 3;
          RtlLogUnexpectedCodepath(&v19);
          DpRegion::~DpRegion((DpRegion *)&v14);
          goto LABEL_8;
        }
        DpRegion::~DpRegion((DpRegion *)&v14);
      }
      ++v6;
      v7 += 4;
    }
    while ( v6 < a3 );
  }
  *a1 = 1733452849;
  v12 = DpRegion::Set(a1, v18, 0);
LABEL_8:
  DpRegion::~DpRegion((DpRegion *)v18);
  return v12;
}

```

## disassembly

```asm
0x18013cf28  mov     [rsp-8+arg_10], rbx
0x18013cf2d  mov     [rsp-8+arg_18], rsi
0x18013cf32  push    rbp
0x18013cf33  push    rdi
0x18013cf34  push    r12
0x18013cf36  push    r14
0x18013cf38  push    r15
0x18013cf3a  lea     rbp, [rsp-37h]
0x18013cf3f  sub     rsp, 0A0h
0x18013cf46  mov     rax, cs:__security_cookie
0x18013cf4d  xor     rax, rsp
0x18013cf50  mov     [rbp+57h+var_30], rax
0x18013cf54  and     [rbp+57h+var_38], 0
0x18013cf58  mov     r14, rcx
0x18013cf5b  lea     rcx, [rbp+57h+var_40]
0x18013cf5f  mov     [rbp+57h+var_40], 3582D32h
0x18013cf66  mov     r12d, r8d
0x18013cf69  mov     [rbp+57h+var_3C], 2
0x18013cf70  mov     r15, rdx
0x18013cf73  call    cs:__imp_RtlLogUnexpectedCodepath
0x18013cf7a  nop     dword ptr [rax+rax+00h]
0x18013cf7f  mov     edx, 1; int
0x18013cf84  lea     rcx, [rbp+57h+var_68]; this
0x18013cf88  call    ??0DpRegion@@QEAA@H@Z; DpRegion::DpRegion(int)
0x18013cf8d  xor     ebx, ebx
0x18013cf8f  test    r12d, r12d
0x18013cf92  jle     short loc_18013D005
0x18013cf94  lea     rdi, [r15+4]
0x18013cf98  movsxd  rcx, ebx
0x18013cf9b  shl     rcx, 4
0x18013cf9f  add     rcx, r15
0x18013cfa2  call    IsRectValid
0x18013cfa7  test    eax, eax
0x18013cfa9  jz      short loc_18013CFFA
0x18013cfab  mov     eax, [rdi+8]
0x18013cfae  lea     rcx, [rbp+57h+var_90]; this
0x18013cfb2  mov     r9d, [rdi+4]
0x18013cfb6  sub     eax, [rdi]
0x18013cfb8  mov     edx, [rdi-4]; int
0x18013cfbb  sub     r9d, edx; int
0x18013cfbe  mov     r8d, [rdi]; int
0x18013cfc1  and     [rbp+57h+var_78], 0
0x18013cfc6  and     [rbp+57h+var_8C], 0FFFFFFFBh
0x18013cfca  and     [rbp+57h+var_70], 0
0x18013cfce  mov     [rsp+0C0h+var_A0], eax; int
0x18013cfd2  mov     [rbp+57h+var_90], 67526431h
0x18013cfd9  call    ?Set@DpRegion@@QEAAXHHHH@Z; DpRegion::Set(int,int,int,int)
0x18013cfde  lea     rdx, [rbp+57h+var_90]
0x18013cfe2  lea     rcx, [rbp+57h+var_68]
0x18013cfe6  call    ?Or@DpRegion@@QEAA?AW4Status@@PEBV1@@Z; DpRegion::Or(DpRegion const *)
0x18013cfeb  mov     esi, eax
0x18013cfed  test    eax, eax
0x18013cfef  jnz     short loc_18013D051
0x18013cff1  lea     rcx, [rbp+57h+var_90]; this
0x18013cff5  call    ??1DpRegion@@QEAA@XZ; DpRegion::~DpRegion(void)
0x18013cffa  inc     ebx
0x18013cffc  add     rdi, 10h
0x18013d000  cmp     ebx, r12d
0x18013d003  jl      short loc_18013CF98
0x18013d005  xor     r8d, r8d
0x18013d008  mov     dword ptr [r14], 67526431h
0x18013d00f  lea     rdx, [rbp+57h+var_68]
0x18013d013  mov     rcx, r14
0x18013d016  call    ?Set@DpRegion@@QEAA?AW4Status@@PEBV1@H@Z; DpRegion::Set(DpRegion const *,int)
0x18013d01b  mov     esi, eax
0x18013d01d  lea     rcx, [rbp+57h+var_68]; this
0x18013d021  call    ??1DpRegion@@QEAA@XZ; DpRegion::~DpRegion(void)
0x18013d026  mov     eax, esi
0x18013d028  mov     rcx, [rbp+57h+var_30]
0x18013d02c  xor     rcx, rsp; StackCookie
0x18013d02f  call    __security_check_cookie
0x18013d034  lea     r11, [rsp+0C0h+var_20]
0x18013d03c  mov     rbx, [r11+40h]
0x18013d040  mov     rsi, [r11+48h]
0x18013d044  mov     rsp, r11
0x18013d047  pop     r15
0x18013d049  pop     r14
0x18013d04b  pop     r12
0x18013d04d  pop     rdi
0x18013d04e  pop     rbp
0x18013d04f  retn
0x18013d051  and     [rbp+57h+var_38], 0
0x18013d055  lea     rcx, [rbp+57h+var_40]
0x18013d059  mov     [rbp+57h+var_40], 3582D32h
0x18013d060  mov     [rbp+57h+var_3C], 3
0x18013d067  call    cs:__imp_RtlLogUnexpectedCodepath
0x18013d06e  nop     dword ptr [rax+rax+00h]
0x18013d073  lea     rcx, [rbp+57h+var_90]; this
0x18013d077  call    ??1DpRegion@@QEAA@XZ; DpRegion::~DpRegion(void)
0x18013d07c  jmp     short loc_18013D01D
```
