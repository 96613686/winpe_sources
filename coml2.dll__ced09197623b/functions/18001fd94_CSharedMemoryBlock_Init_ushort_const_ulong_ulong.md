# CSharedMemoryBlock::Init(ushort const *,ulong,ulong)

- ea: `0x18001fd94`
- end: `0x18001ff10`
- name: `?Init@CSharedMemoryBlock@@QEAAJPEBGKK@Z`
- size: `380`
- prototype: `int(CSharedMemoryBlock *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f5cc`

## callees

- `0x18001fd94`
- `0x18001ff18`
- `0x180020044`
- `0x180034ad8`
- `0x18003f54c`
- `0x18003f62c`
- `0x180042800`
- `0x18004388c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001fe3f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001fe3f`

## string_xrefs

- `0x18001fe90`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x18001feb0`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x18001fecb`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x18001feee`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`

## pseudocode

```c
__int64 __fastcall CSharedMemoryBlock::Init(void **this, const unsigned __int16 *a2, int a3, unsigned int a4)
{
  int v7; // eax
  const unsigned __int16 *v8; // rcx
  __int64 v9; // r8
  void *v10; // r9
  unsigned int v11; // ebx
  LPVOID *v12; // rsi
  HANDLE v13; // rax
  const char *v14; // r9
  CSharedMemoryBlock *v15; // rbx
  const char *v16; // r9
  char *v17; // rcx
  unsigned int LastError; // edi
  int v20; // [rsp+20h] [rbp-238h]
  int v21; // [rsp+20h] [rbp-238h]
  unsigned int v22; // [rsp+28h] [rbp-230h]
  int v23; // [rsp+40h] [rbp-218h] BYREF
  _BYTE v24[8]; // [rsp+48h] [rbp-210h] BYREF
  _BYTE v25[176]; // [rsp+50h] [rbp-208h] BYREF
  int v26[72]; // [rsp+100h] [rbp-158h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v7 = CSharedMemoryMarshalingSecurityDescriptor::Init((CSharedMemoryMarshalingSecurityDescriptor *)v25, 0xF001Fu);
  v11 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
      (const char *)(unsigned int)v7,
      v20);
    return v11;
  }
  else
  {
    v23 = 0;
    v12 = this + 1;
    v13 = CreateSharedFileMapping(v8, a3 + 24, v9, v10, v26, v22, this + 1, &v23);
    *this = v13;
    if ( v13 )
    {
      v15 = *(CSharedMemoryBlock **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                      v24,
                                      this);
      if ( v23 )
      {
        if ( VirtualAlloc(*v12, a4, 0x1000u, 4u) )
        {
          v17 = (char *)*v12;
          *((_DWORD *)this + 4) = a4;
          *((_DWORD *)this + 5) = a4;
          *(GUID *)(v17 + 8) = GUID_edc0cbd7_ba5f_49c2_b7ff_6cbeb1cc2dac;
          *(_DWORD *)v17 = *((_DWORD *)this + 4);
          return 0;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x6B,
                      (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
                      v16);
      }
      else
      {
        LastError = -2147286784;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
          (const char *)0x80030100LL,
          v21);
      }
      CSharedMemoryBlock::CloseMapping(v15);
      return LastError;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x54,
               (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
               v14);
    }
  }
}

```

## disassembly

```asm
0x18001fd94  push    rbx
0x18001fd96  push    rbp
0x18001fd97  push    rsi
0x18001fd98  push    rdi
0x18001fd99  push    r14
0x18001fd9b  sub     rsp, 230h
0x18001fda2  mov     rax, cs:__security_cookie
0x18001fda9  xor     rax, rsp
0x18001fdac  mov     [rsp+258h+var_38], rax
0x18001fdb4  mov     rdi, rcx
0x18001fdb7  mov     ebp, r9d
0x18001fdba  lea     rcx, [rsp+258h+var_208]; this
0x18001fdbf  mov     edx, 0F001Fh; AccessMask
0x18001fdc4  mov     r14d, r8d
0x18001fdc7  call    ?Init@CSharedMemoryMarshalingSecurityDescriptor@@QEAAJK@Z; CSharedMemoryMarshalingSecurityDescriptor::Init(ulong)
0x18001fdcc  mov     ebx, eax
0x18001fdce  test    eax, eax
0x18001fdd0  js      loc_18001FE88
0x18001fdd6  lea     rax, [rsp+258h+var_218]
0x18001fddb  mov     [rsp+258h+var_218], 0
0x18001fde3  mov     [rsp+258h+var_220], rax; int *
0x18001fde8  lea     rsi, [rdi+8]
0x18001fdec  lea     rax, [rsp+258h+var_158]
0x18001fdf4  mov     [rsp+258h+var_228], rsi; void **
0x18001fdf9  lea     edx, [r14+18h]; unsigned int
0x18001fdfd  mov     [rsp+258h+var_238], rax; int
0x18001fe02  call    ?CreateSharedFileMapping@@YAPEAXPEBGKKPEAX1KPEAPEAXPEAH@Z; CreateSharedFileMapping(ushort const *,ulong,ulong,void *,void *,ulong,void * *,int *)
0x18001fe07  mov     [rdi], rax
0x18001fe0a  test    rax, rax
0x18001fe0d  jz      loc_18001FEA8
0x18001fe13  mov     rdx, rdi
0x18001fe16  lea     rcx, [rsp+258h+var_210]
0x18001fe1b  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001fe20  cmp     [rsp+258h+var_218], 0
0x18001fe25  mov     rbx, [rax]
0x18001fe28  jz      loc_18001FEC3
0x18001fe2e  mov     rcx, [rsi]; lpAddress
0x18001fe31  mov     edx, ebp; dwSize
0x18001fe33  mov     r9d, 4; flProtect
0x18001fe39  mov     r8d, 1000h; flAllocationType
0x18001fe3f  call    cs:__imp_VirtualAlloc
0x18001fe45  test    rax, rax
0x18001fe48  jz      loc_18001FEE6
0x18001fe4e  mov     rcx, [rsi]
0x18001fe51  mov     [rdi+10h], ebp
0x18001fe54  mov     [rdi+14h], ebp
0x18001fe57  movups  xmm0, xmmword ptr cs:_GUID_edc0cbd7_ba5f_49c2_b7ff_6cbeb1cc2dac.Data1
0x18001fe5e  movdqu  xmmword ptr [rcx+8], xmm0
0x18001fe63  mov     eax, [rdi+10h]
0x18001fe66  mov     [rcx], eax
0x18001fe68  xor     eax, eax
0x18001fe6a  mov     rcx, [rsp+258h+var_38]
0x18001fe72  xor     rcx, rsp; StackCookie
0x18001fe75  call    __security_check_cookie
0x18001fe7a  add     rsp, 230h
0x18001fe81  pop     r14
0x18001fe83  pop     rdi
0x18001fe84  pop     rsi
0x18001fe85  pop     rbp
0x18001fe86  pop     rbx
0x18001fe87  retn
0x18001fe88  mov     rcx, [rsp+258h]; this
0x18001fe90  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x18001fe97  mov     r9d, ebx; char *
0x18001fe9a  mov     edx, 48h ; 'H'; void *
0x18001fe9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fea4  mov     eax, ebx
0x18001fea6  jmp     short loc_18001FE6A
0x18001fea8  mov     rcx, [rsp+258h]; this
0x18001feb0  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x18001feb7  mov     edx, 54h ; 'T'; void *
0x18001febc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fec1  jmp     short loc_18001FE6A
0x18001fec3  mov     rcx, [rsp+258h]; this
0x18001fecb  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x18001fed2  mov     edi, 80030100h
0x18001fed7  mov     edx, 5Bh ; '['; void *
0x18001fedc  mov     r9d, edi; char *
0x18001fedf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fee4  jmp     short loc_18001FF01
0x18001fee6  mov     rcx, [rsp+258h]; this
0x18001feee  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x18001fef5  mov     edx, 6Bh ; 'k'; void *
0x18001fefa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001feff  mov     edi, eax
0x18001ff01  mov     rcx, rbx; this
0x18001ff04  call    ?CloseMapping@CSharedMemoryBlock@@AEAAXXZ; CSharedMemoryBlock::CloseMapping(void)
0x18001ff09  mov     eax, edi
0x18001ff0b  jmp     loc_18001FE6A
```
