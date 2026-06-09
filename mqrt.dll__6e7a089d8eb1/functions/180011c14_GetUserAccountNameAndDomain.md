# _GetUserAccountNameAndDomain

- ea: `0x180011c14`
- end: `0x180011fdd`
- name: `_GetUserAccountNameAndDomain`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800120b0`

## callees

- `0x180006fdc`
- `0x180011c14`
- `0x180013c74`
- `0x180021010`
- `0x180023ca0`

## import_xrefs

- `msvcrt!free` at `0x180011cba`
- `msvcrt!free` at `0x180011cc3`
- `msvcrt!free` at `0x180011ccc`
- `msvcrt!free` at `0x180011d13`
- `msvcrt!free` at `0x180011d1c`
- `msvcrt!free` at `0x180011d25`
- `msvcrt!free` at `0x180011e42`
- `msvcrt!free` at `0x180011e4c`
- `msvcrt!free` at `0x180011e56`
- `msvcrt!free` at `0x180011e83`
- `msvcrt!free` at `0x180011e8c`
- `msvcrt!free` at `0x180011e95`
- `msvcrt!free` at `0x180011f17`
- `msvcrt!free` at `0x180011f21`
- `msvcrt!free` at `0x180011f2b`
- `msvcrt!free` at `0x180011f98`
- `msvcrt!free` at `0x180011fa2`
- `msvcrt!free` at `0x180011fac`
- `msvcrt!free` at `0x180011cba`
- `msvcrt!free` at `0x180011cc3`
- `msvcrt!free` at `0x180011ccc`
- `msvcrt!free` at `0x180011d13`
- `msvcrt!free` at `0x180011d1c`
- `msvcrt!free` at `0x180011d25`
- `msvcrt!free` at `0x180011e42`
- `msvcrt!free` at `0x180011e4c`
- `msvcrt!free` at `0x180011e56`
- `msvcrt!free` at `0x180011e83`
- `msvcrt!free` at `0x180011e8c`
- `msvcrt!free` at `0x180011e95`
- `msvcrt!free` at `0x180011f17`
- `msvcrt!free` at `0x180011f21`
- `msvcrt!free` at `0x180011f2b`
- `msvcrt!free` at `0x180011f98`
- `msvcrt!free` at `0x180011fa2`
- `msvcrt!free` at `0x180011fac`
- `ADVAPI32!LookupAccountSidW` at `0x180011d73`
- `ADVAPI32!LookupAccountSidW` at `0x180011e17`
- `ADVAPI32!LookupAccountSidW` at `0x180011d73`
- `ADVAPI32!LookupAccountSidW` at `0x180011e17`
- `KERNEL32!GetLastError` at `0x180011d81`
- `KERNEL32!GetLastError` at `0x180011d81`
- `mqsec!MQSec_GetLocalMachineSid` at `0x180011c8b`
- `mqsec!MQSec_GetLocalMachineSid` at `0x180011c8b`
- `mqsec!MQSec_GetThreadUserSid` at `0x180011ce9`
- `mqsec!MQSec_GetThreadUserSid` at `0x180011ce9`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall GetUserAccountNameAndDomain(int a1, wchar_t **a2, wchar_t **a3)
{
  WCHAR *v3; // r13
  WCHAR *v4; // rdi
  WCHAR *v5; // r12
  WCHAR *v6; // rbx
  void *LocalMachineSid; // rsi
  int ThreadUserSid; // eax
  unsigned int v10; // esi
  wchar_t *v11; // rax
  int v12; // eax
  unsigned int v13; // esi
  wchar_t *v14; // rax
  DWORD cchName; // [rsp+40h] [rbp-178h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-174h] BYREF
  void *Block; // [rsp+48h] [rbp-170h] BYREF
  int v18; // [rsp+50h] [rbp-168h]
  enum _SID_NAME_USE peUse; // [rsp+54h] [rbp-164h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-160h] BYREF
  WCHAR *v21; // [rsp+60h] [rbp-158h]
  WCHAR *v22; // [rsp+68h] [rbp-150h]
  wchar_t **v23; // [rsp+70h] [rbp-148h]
  wchar_t **v24; // [rsp+78h] [rbp-140h]
  WCHAR ReferencedDomainName[64]; // [rsp+80h] [rbp-138h] BYREF
  WCHAR Name[64]; // [rsp+100h] [rbp-B8h] BYREF

  v24 = a3;
  v23 = a2;
  v18 = 0;
  cchName = 64;
  v3 = Name;
  v4 = 0;
  v21 = 0;
  cchReferencedDomainName = 64;
  v5 = ReferencedDomainName;
  v6 = 0;
  v22 = 0;
  Block = 0;
  v20 = 0;
  if ( a1 )
  {
    LocalMachineSid = MQSec_GetLocalMachineSid(0, 0);
    if ( !LocalMachineSid )
    {
      LogMsgHR(-1072824265, (wchar_t *)L"rt/rtintcrt", 0xAu);
      free(Block);
      free(0);
      free(0);
      return 3222143031LL;
    }
  }
  else
  {
    ThreadUserSid = MQSec_GetThreadUserSid(0, &Block, &v20, 0);
    v10 = ThreadUserSid;
    v18 = ThreadUserSid;
    if ( ThreadUserSid < 0 )
    {
      LogMsgHR(ThreadUserSid, (wchar_t *)L"rt/rtintcrt", 0x14u);
      free(Block);
      free(0);
      free(0);
      return v10;
    }
    LocalMachineSid = Block;
  }
  peUse = 0;
  if ( !LookupAccountSidW(0, LocalMachineSid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    if ( GetLastError() != 122 )
    {
      LogMsgHR(-1072824265, (wchar_t *)L"rt/rtintcrt", 0x28u);
      free(Block);
      free(0);
      free(0);
      return 3222143031LL;
    }
    if ( cchName > 0x40 )
    {
      v3 = (WCHAR *)MmAllocate(saturated_mul(cchName, 2u));
      v4 = v3;
      v21 = v3;
    }
    if ( cchReferencedDomainName > 0x40 )
    {
      v5 = (WCHAR *)MmAllocate(saturated_mul(cchReferencedDomainName, 2u));
      v6 = v5;
      v22 = v5;
    }
    if ( !LookupAccountSidW(0, LocalMachineSid, v3, &cchName, v5, &cchReferencedDomainName, &peUse) )
    {
      LogMsgHR(-1072824265, (wchar_t *)L"rt/rtintcrt", 0x1Eu);
      free(Block);
      free(v6);
      free(v4);
      return 3222143031LL;
    }
  }
  v11 = (wchar_t *)MmAllocate(saturated_mul(cchName + 1, 2u));
  *v23 = v11;
  v12 = StringCchCopyW(v11, cchName + 1, v3);
  v13 = v12;
  v18 = v12;
  if ( v12 >= 0 )
  {
    v14 = (wchar_t *)MmAllocate(saturated_mul(cchReferencedDomainName + 1, 2u));
    *v24 = v14;
    StringCchCopyW(v14, cchReferencedDomainName + 1, v5);
    free(Block);
    free(v6);
    free(v4);
    return v13;
  }
  else
  {
    LogMsgHR(v12, (wchar_t *)L"rt/rtintcrt", 0x2Au);
    LogMsgHR(-1072824265, (wchar_t *)L"rt/rtintcrt", 0x2Bu);
    free(Block);
    free(v6);
    free(v4);
    return 3222143031LL;
  }
}

```

## disassembly

```asm
0x180011c14  mov     [rsp+arg_0], rbx
0x180011c19  push    rsi
0x180011c1a  push    rdi
0x180011c1b  push    r12
0x180011c1d  push    r13
0x180011c1f  push    r15
0x180011c21  sub     rsp, 190h
0x180011c28  mov     rax, cs:__security_cookie
0x180011c2f  xor     rax, rsp
0x180011c32  mov     [rsp+1B8h+var_38], rax
0x180011c3a  mov     [rsp+1B8h+var_140], r8
0x180011c3f  mov     [rsp+1B8h+var_148], rdx
0x180011c44  mov     [rsp+1B8h+var_168], 0
0x180011c4c  mov     [rsp+1B8h+cchName], 40h ; '@'
0x180011c54  lea     r13, [rsp+1B8h+Name]
0x180011c5c  xor     edi, edi
0x180011c5e  mov     [rsp+1B8h+var_158], rdi
0x180011c63  mov     [rsp+1B8h+var_174], 40h ; '@'
0x180011c6b  lea     r12, [rsp+1B8h+var_138]
0x180011c73  xor     ebx, ebx
0x180011c75  mov     [rsp+1B8h+var_150], rbx
0x180011c7a  mov     [rsp+1B8h+Block], rbx
0x180011c7f  mov     [rsp+1B8h+var_160], ebx
0x180011c83  test    ecx, ecx
0x180011c85  jz      short loc_180011CDA
0x180011c87  xor     edx, edx
0x180011c89  xor     ecx, ecx
0x180011c8b  call    cs:__imp_?MQSec_GetLocalMachineSid@@YAPEAXHPEAK@Z; MQSec_GetLocalMachineSid(int,ulong *)
0x180011c91  mov     rsi, rax
0x180011c94  test    rax, rax
0x180011c97  jnz     loc_180011D38
0x180011c9d  lea     r8d, [rdi+0Ah]; unsigned __int16
0x180011ca1  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011ca8  mov     esi, 0C00E0037h
0x180011cad  mov     ecx, esi; int
0x180011caf  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011cb4  nop
0x180011cb5  mov     rcx, [rsp+1B8h+Block]; Block
0x180011cba  call    cs:__imp_free
0x180011cc0  nop
0x180011cc1  xor     ecx, ecx; Block
0x180011cc3  call    cs:__imp_free
0x180011cc9  nop
0x180011cca  xor     ecx, ecx; Block
0x180011ccc  call    cs:__imp_free
0x180011cd2  nop
0x180011cd3  mov     eax, esi
0x180011cd5  jmp     loc_180011FB5
0x180011cda  xor     r9d, r9d
0x180011cdd  lea     r8, [rsp+1B8h+var_160]
0x180011ce2  lea     rdx, [rsp+1B8h+Block]
0x180011ce7  xor     ecx, ecx
0x180011ce9  call    cs:__imp_?MQSec_GetThreadUserSid@@YAJHPEAPEAXPEAKH@Z; MQSec_GetThreadUserSid(int,void * *,ulong *,int)
0x180011cef  mov     esi, eax
0x180011cf1  mov     [rsp+1B8h+var_168], eax
0x180011cf5  test    eax, eax
0x180011cf7  jns     short loc_180011D33
0x180011cf9  mov     r8d, 14h; unsigned __int16
0x180011cff  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011d06  mov     ecx, eax; int
0x180011d08  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011d0d  nop
0x180011d0e  mov     rcx, [rsp+1B8h+Block]; Block
0x180011d13  call    cs:__imp_free
0x180011d19  nop
0x180011d1a  xor     ecx, ecx; Block
0x180011d1c  call    cs:__imp_free
0x180011d22  nop
0x180011d23  xor     ecx, ecx; Block
0x180011d25  call    cs:__imp_free
0x180011d2b  nop
0x180011d2c  mov     eax, esi
0x180011d2e  jmp     loc_180011FB5
0x180011d33  mov     rsi, [rsp+1B8h+Block]
0x180011d38  mov     [rsp+1B8h+var_164], 0
0x180011d40  lea     rax, [rsp+1B8h+var_164]
0x180011d45  mov     [rsp+1B8h+peUse], rax; peUse
0x180011d4a  lea     rax, [rsp+1B8h+var_174]
0x180011d4f  mov     [rsp+1B8h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180011d54  lea     rax, [rsp+1B8h+var_138]
0x180011d5c  mov     [rsp+1B8h+ReferencedDomainName], rax; ReferencedDomainName
0x180011d61  lea     r9, [rsp+1B8h+cchName]; cchName
0x180011d66  lea     r8, [rsp+1B8h+Name]; Name
0x180011d6e  mov     rdx, rsi; Sid
0x180011d71  xor     ecx, ecx; lpSystemName
0x180011d73  call    cs:__imp_LookupAccountSidW
0x180011d79  test    eax, eax
0x180011d7b  jnz     loc_180011EA3
0x180011d81  call    cs:__imp_GetLastError
0x180011d87  cmp     eax, 7Ah ; 'z'
0x180011d8a  jnz     loc_180011E64
0x180011d90  cmp     [rsp+1B8h+cchName], 40h ; '@'
0x180011d95  jbe     short loc_180011DC3
0x180011d97  mov     ecx, [rsp+1B8h+cchName]
0x180011d9b  mov     eax, 2
0x180011da0  mul     rcx
0x180011da3  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180011daa  cmovb   rax, r15
0x180011dae  mov     rcx, rax; unsigned __int64
0x180011db1  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011db6  mov     r13, rax
0x180011db9  mov     rdi, rax
0x180011dbc  mov     [rsp+1B8h+var_158], rax
0x180011dc1  jmp     short loc_180011DC7
0x180011dc3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180011dc7  cmp     [rsp+1B8h+var_174], 40h ; '@'
0x180011dcc  jbe     short loc_180011DF1
0x180011dce  mov     ecx, [rsp+1B8h+var_174]
0x180011dd2  mov     eax, 2
0x180011dd7  mul     rcx
0x180011dda  cmovb   rax, r15
0x180011dde  mov     rcx, rax; unsigned __int64
0x180011de1  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011de6  mov     r12, rax
0x180011de9  mov     rbx, rax
0x180011dec  mov     [rsp+1B8h+var_150], rax
0x180011df1  lea     rax, [rsp+1B8h+var_164]
0x180011df6  mov     [rsp+1B8h+peUse], rax; peUse
0x180011dfb  lea     rax, [rsp+1B8h+var_174]
0x180011e00  mov     [rsp+1B8h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180011e05  mov     [rsp+1B8h+ReferencedDomainName], r12; ReferencedDomainName
0x180011e0a  lea     r9, [rsp+1B8h+cchName]; cchName
0x180011e0f  mov     r8, r13; Name
0x180011e12  mov     rdx, rsi; Sid
0x180011e15  xor     ecx, ecx; lpSystemName
0x180011e17  call    cs:__imp_LookupAccountSidW
0x180011e1d  test    eax, eax
0x180011e1f  jnz     loc_180011EA7
0x180011e25  lea     r8d, [rax+1Eh]; unsigned __int16
0x180011e29  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011e30  mov     esi, 0C00E0037h
0x180011e35  mov     ecx, esi; int
0x180011e37  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011e3c  nop
0x180011e3d  mov     rcx, [rsp+1B8h+Block]; Block
0x180011e42  call    cs:__imp_free
0x180011e48  nop
0x180011e49  mov     rcx, rbx; Block
0x180011e4c  call    cs:__imp_free
0x180011e52  nop
0x180011e53  mov     rcx, rdi; Block
0x180011e56  call    cs:__imp_free
0x180011e5c  nop
0x180011e5d  mov     eax, esi
0x180011e5f  jmp     loc_180011FB5
0x180011e64  mov     r8d, 28h ; '('; unsigned __int16
0x180011e6a  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011e71  mov     esi, 0C00E0037h
0x180011e76  mov     ecx, esi; int
0x180011e78  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011e7d  nop
0x180011e7e  mov     rcx, [rsp+1B8h+Block]; Block
0x180011e83  call    cs:__imp_free
0x180011e89  nop
0x180011e8a  xor     ecx, ecx; Block
0x180011e8c  call    cs:__imp_free
0x180011e92  nop
0x180011e93  xor     ecx, ecx; Block
0x180011e95  call    cs:__imp_free
0x180011e9b  nop
0x180011e9c  mov     eax, esi
0x180011e9e  jmp     loc_180011FB5
0x180011ea3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180011ea7  mov     ecx, [rsp+1B8h+cchName]
0x180011eab  inc     ecx
0x180011ead  mov     eax, 2
0x180011eb2  mul     rcx
0x180011eb5  cmovb   rax, r15
0x180011eb9  mov     rcx, rax; unsigned __int64
0x180011ebc  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011ec1  mov     rcx, [rsp+1B8h+var_148]
0x180011ec6  mov     [rcx], rax
0x180011ec9  mov     edx, [rsp+1B8h+cchName]
0x180011ecd  inc     edx; unsigned __int64
0x180011ecf  mov     r8, r13; wchar_t *
0x180011ed2  mov     rcx, rax; wchar_t *
0x180011ed5  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180011eda  mov     esi, eax
0x180011edc  mov     [rsp+1B8h+var_168], eax
0x180011ee0  test    eax, eax
0x180011ee2  jns     short loc_180011F36
0x180011ee4  mov     r8d, 2Ah ; '*'; unsigned __int16
0x180011eea  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011ef1  mov     ecx, eax; int
0x180011ef3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011ef8  mov     r8d, 2Bh ; '+'; unsigned __int16
0x180011efe  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011f05  mov     esi, 0C00E0037h
0x180011f0a  mov     ecx, esi; int
0x180011f0c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011f11  nop
0x180011f12  mov     rcx, [rsp+1B8h+Block]; Block
0x180011f17  call    cs:__imp_free
0x180011f1d  nop
0x180011f1e  mov     rcx, rbx; Block
0x180011f21  call    cs:__imp_free
0x180011f27  nop
0x180011f28  mov     rcx, rdi; Block
0x180011f2b  call    cs:__imp_free
0x180011f31  nop
0x180011f32  mov     eax, esi
0x180011f34  jmp     short loc_180011FB5
0x180011f36  mov     edx, [rsp+1B8h+var_174]
0x180011f3a  inc     edx
0x180011f3c  mov     eax, 2
0x180011f41  mul     rdx
0x180011f44  cmovb   rax, r15
0x180011f48  mov     rcx, rax; unsigned __int64
0x180011f4b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011f50  mov     rcx, [rsp+1B8h+var_140]
0x180011f55  mov     [rcx], rax
0x180011f58  mov     edx, [rsp+1B8h+var_174]
0x180011f5c  inc     edx; unsigned __int64
0x180011f5e  mov     r8, r12; wchar_t *
0x180011f61  mov     rcx, rax; wchar_t *
0x180011f64  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180011f69  nop
0x180011f6a  jmp     short loc_180011F7A
0x180011f6c  mov     esi, [rsp+1B8h+var_168]
0x180011f70  mov     rdi, [rsp+1B8h+var_158]
0x180011f75  mov     rbx, [rsp+1B8h+var_150]
0x180011f7a  test    esi, esi
0x180011f7c  jns     short loc_180011F93
0x180011f7e  mov     r8d, 46h ; 'F'; unsigned __int16
0x180011f84  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180011f8b  mov     ecx, esi; int
0x180011f8d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011f92  nop
0x180011f93  mov     rcx, [rsp+1B8h+Block]; Block
0x180011f98  call    cs:__imp_free
0x180011f9e  nop
0x180011f9f  mov     rcx, rbx; Block
0x180011fa2  call    cs:__imp_free
0x180011fa8  nop
0x180011fa9  mov     rcx, rdi; Block
0x180011fac  call    cs:__imp_free
0x180011fb2  nop
0x180011fb3  mov     eax, esi
0x180011fb5  mov     rcx, [rsp+1B8h+var_38]
0x180011fbd  xor     rcx, rsp; StackCookie
0x180011fc0  call    __security_check_cookie
0x180011fc5  mov     rbx, [rsp+1B8h+arg_0]
0x180011fcd  add     rsp, 190h
0x180011fd4  pop     r15
0x180011fd6  pop     r13
0x180011fd8  pop     r12
0x180011fda  pop     rdi
0x180011fdb  pop     rsi
0x180011fdc  retn
```
