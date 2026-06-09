# CNat::CreateRedirect(ulong,uchar,ulong,ushort,ulong,ushort,ulong,ushort,ulong,ushort,ulong,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180082180`
- end: `0x180082792`
- name: `?CreateRedirect@CNat@@UEAAJKEKGKGKGKGK_K00@Z`
- size: `1554`
- prototype: `signed int __fastcall(void **this, int, unsigned __int8, int, unsigned __int16, struct in_addr in, u_short, struct in_addr, u_short, struct in_addr, u_short, unsigned int, unsigned __int64 dwProcessId, HANDLE hSourceHandle, HANDLE)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180012430`
- `0x180012730`
- `0x180031790`
- `0x180057140`
- `0x180082180`
- `0x180082d98`
- `0x18008339c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008243b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008243b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180082466`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008256a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180082466`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008256a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180082491`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180082595`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180082491`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180082595`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800824d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800825e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008264f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082714`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800824d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800825e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008264f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082714`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082723`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800823f8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800823f8`
- `WS2_32!__imp_inet_ntoa` at `0x180082289`
- `WS2_32!__imp_inet_ntoa` at `0x1800822e5`
- `WS2_32!__imp_inet_ntoa` at `0x180082344`
- `WS2_32!__imp_inet_ntoa` at `0x18008239c`
- `WS2_32!__imp_inet_ntoa` at `0x180082289`
- `WS2_32!__imp_inet_ntoa` at `0x1800822e5`
- `WS2_32!__imp_inet_ntoa` at `0x180082344`
- `WS2_32!__imp_inet_ntoa` at `0x18008239c`
- `WS2_32!__imp_ntohs` at `0x18008227e`
- `WS2_32!__imp_ntohs` at `0x1800822d9`
- `WS2_32!__imp_ntohs` at `0x180082338`
- `WS2_32!__imp_ntohs` at `0x180082390`
- `WS2_32!__imp_ntohs` at `0x18008227e`
- `WS2_32!__imp_ntohs` at `0x1800822d9`
- `WS2_32!__imp_ntohs` at `0x180082338`
- `WS2_32!__imp_ntohs` at `0x180082390`

## pseudocode

```c
signed int __fastcall CNat::CreateRedirect(
        void **this,
        int a2,
        unsigned __int8 a3,
        int a4,
        unsigned __int16 a5,
        struct in_addr in,
        u_short a7,
        struct in_addr a8,
        u_short a9,
        struct in_addr a10,
        u_short a11,
        unsigned int a12,
        unsigned __int64 dwProcessId,
        HANDLE hSourceHandle,
        HANDLE a15)
{
  unsigned int v16; // esi
  char v18; // r14
  signed int result; // eax
  PVOID *v20; // rcx
  unsigned __int8 v21; // al
  char v22; // bl
  unsigned int v23; // eax
  char v24; // bl
  unsigned int v25; // eax
  char v26; // bl
  unsigned int v27; // eax
  char v28; // bl
  unsigned int v29; // eax
  HANDLE v30; // rbx
  HANDLE CurrentProcess; // rax
  __int64 v32; // r8
  PVOID *v33; // rcx
  HANDLE v34; // rax
  __int64 v35; // r8
  HANDLE v36; // rbx
  HANDLE Event; // rdi
  void *TranslatorHandle; // rax
  signed int Redirect; // ebx
  HANDLE TargetHandle; // [rsp+88h] [rbp-9h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-1h] BYREF

  v16 = a3;
  v18 = 6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
  }
  if ( !CNat::IsClientAllowedToCallUs(this) )
    return -2147024891;
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      if ( (_BYTE)v16 == 1 )
      {
        v21 = 6;
      }
      else
      {
        v21 = v16;
        if ( (_BYTE)v16 == 2 )
          v21 = 17;
      }
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, v16, v21);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v20 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
      {
        v22 = ntohs(a5);
        v23 = (unsigned int)inet_ntoa((struct in_addr)a4);
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_8ab209e1ee763061284517a200f37d51_Traceguids,
          v23,
          v22);
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v20 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
        {
          v24 = ntohs(a7);
          v25 = (unsigned int)inet_ntoa(in);
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            (unsigned int)&WPP_8ab209e1ee763061284517a200f37d51_Traceguids,
            v25,
            v24);
          v20 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v20 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
          {
            v26 = ntohs(a9);
            v27 = (unsigned int)inet_ntoa(a8);
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              (unsigned int)&WPP_8ab209e1ee763061284517a200f37d51_Traceguids,
              v27,
              v26);
            v20 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
          {
            v28 = ntohs(a11);
            v29 = (unsigned int)inet_ntoa(a10);
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              (unsigned int)&WPP_8ab209e1ee763061284517a200f37d51_Traceguids,
              v29,
              v28);
            v20 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
      }
    }
  }
  TargetHandle = 0;
  hObject = 0;
  if ( !dwProcessId )
  {
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
      WPP_SF_(v20[2], 40, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
    goto LABEL_76;
  }
  v30 = OpenProcess(0x40u, 0, dwProcessId);
  if ( !v30 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, 0);
    }
    goto LABEL_37;
  }
  if ( hSourceHandle )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v30, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, 0);
      }
LABEL_45:
      CloseHandle(v30);
LABEL_37:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    v33 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_55;
    }
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v32, TargetHandle, hSourceHandle);
  }
  else
  {
    v33 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_55;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
  }
  v33 = (PVOID *)WPP_GLOBAL_Control;
LABEL_55:
  if ( a15 )
  {
    v34 = GetCurrentProcess();
    if ( !DuplicateHandle(v30, a15, v34, &hObject, 0, 0, 2u) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids, 0);
      }
      if ( TargetHandle )
        CloseHandle(TargetHandle);
      goto LABEL_45;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v35, hObject, a15);
    }
  }
  else if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 4u )
  {
    WPP_SF_(v33[2], 39, &WPP_8ab209e1ee763061284517a200f37d51_Traceguids);
  }
  CloseHandle(v30);
LABEL_76:
  v36 = TargetHandle;
  Event = hObject;
  if ( (_BYTE)v16 != 1 )
  {
    v18 = v16;
    if ( (_BYTE)v16 == 2 )
      v18 = 17;
  }
  TranslatorHandle = CNat::GetTranslatorHandle((CNat *)this);
  Redirect = NatCreateRedirectEx(
               TranslatorHandle,
               a2,
               v18,
               a4,
               a5,
               in.S_un.S_addr,
               a7,
               a8.S_un.S_addr,
               a9,
               a10.S_un.S_addr,
               a11,
               a12,
               (char *)0xFFFFFFFFFFFFFFFFLL,
               Event,
               (__int64)v36);
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( hObject )
    CloseHandle(hObject);
  if ( !Redirect )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      &WPP_8ab209e1ee763061284517a200f37d51_Traceguids,
      (unsigned int)Redirect);
  }
  if ( Redirect > 0 )
    return (unsigned __int16)Redirect | 0x80070000;
  return Redirect;
}

```

## disassembly

```asm
0x180082180  mov     rax, rsp
0x180082183  mov     [rax+8], rbx
0x180082187  mov     [rax+20h], r9d
0x18008218b  mov     [rax+10h], edx
0x18008218e  push    rbp
0x18008218f  push    rsi
0x180082190  push    rdi
0x180082191  push    r12
0x180082193  push    r13
0x180082195  push    r14
0x180082197  push    r15
0x180082199  lea     rbp, [rax-3Fh]
0x18008219d  sub     rsp, 90h
0x1800821a4  mov     edi, r9d
0x1800821a7  movzx   esi, r8b
0x1800821ab  mov     r15, rcx
0x1800821ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800821b5  lea     rbx, WPP_GLOBAL_Control
0x1800821bc  mov     r14b, 6
0x1800821bf  cmp     rcx, rbx
0x1800821c2  jz      short loc_1800821E5
0x1800821c4  test    byte ptr [rcx+1Ch], 1
0x1800821c8  jz      short loc_1800821E5
0x1800821ca  cmp     [rcx+19h], r14b
0x1800821ce  jb      short loc_1800821E5
0x1800821d0  mov     rcx, [rcx+10h]
0x1800821d4  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800821db  mov     edx, 1Bh
0x1800821e0  call    WPP_SF_
0x1800821e5  mov     rcx, r15; this
0x1800821e8  call    ?IsClientAllowedToCallUs@CNat@@AEAA_NXZ; CNat::IsClientAllowedToCallUs(void)
0x1800821ed  test    al, al
0x1800821ef  jnz     short loc_1800821FB
0x1800821f1  mov     eax, 80070005h
0x1800821f6  jmp     loc_180082777
0x1800821fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180082202  mov     edx, 11h
0x180082207  movzx   r12d, [rbp+37h+arg_50]
0x18008220f  mov     r13d, dword ptr [rbp+37h+arg_48.S_un]
0x180082216  cmp     rcx, rbx
0x180082219  jz      loc_1800823D3
0x18008221f  test    byte ptr [rcx+1Ch], 1
0x180082223  jz      short loc_180082265
0x180082225  cmp     byte ptr [rcx+19h], 4
0x180082229  jb      short loc_180082265
0x18008222b  cmp     sil, 1
0x18008222f  jnz     short loc_180082236
0x180082231  mov     al, r14b
0x180082234  jmp     short loc_18008223F
0x180082236  cmp     sil, 2
0x18008223a  mov     eax, esi
0x18008223c  cmovz   eax, edx
0x18008223f  mov     rcx, [rcx+10h]
0x180082243  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x18008224a  movzx   eax, al
0x18008224d  mov     r9d, esi
0x180082250  mov     edx, 1Ch
0x180082255  mov     [rsp+0C0h+dwDesiredAccess], eax
0x180082259  call    WPP_SF_dd
0x18008225e  mov     rcx, cs:WPP_GLOBAL_Control
0x180082265  cmp     rcx, rbx
0x180082268  jz      loc_1800823D3
0x18008226e  test    byte ptr [rcx+1Ch], 1
0x180082272  jz      short loc_1800822C0
0x180082274  cmp     byte ptr [rcx+19h], 4
0x180082278  jb      short loc_1800822C0
0x18008227a  movzx   ecx, [rbp+37h+arg_20]; netshort
0x18008227e  call    cs:__imp_ntohs
0x180082284  mov     ecx, edi; in
0x180082286  movzx   ebx, ax
0x180082289  call    cs:__imp_inet_ntoa
0x18008228f  mov     rcx, cs:WPP_GLOBAL_Control
0x180082296  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x18008229d  mov     edx, 1Dh
0x1800822a2  mov     [rsp+0C0h+dwDesiredAccess], ebx
0x1800822a6  mov     r9, rax
0x1800822a9  mov     rcx, [rcx+10h]
0x1800822ad  call    WPP_SF_sd
0x1800822b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800822b9  lea     rbx, WPP_GLOBAL_Control
0x1800822c0  cmp     rcx, rbx
0x1800822c3  jz      loc_1800823D3
0x1800822c9  test    byte ptr [rcx+1Ch], 1
0x1800822cd  jz      short loc_18008231C
0x1800822cf  cmp     byte ptr [rcx+19h], 4
0x1800822d3  jb      short loc_18008231C
0x1800822d5  movzx   ecx, [rbp+37h+arg_30]; netshort
0x1800822d9  call    cs:__imp_ntohs
0x1800822df  mov     ecx, dword ptr [rbp+37h+in.S_un]; in
0x1800822e2  movzx   ebx, ax
0x1800822e5  call    cs:__imp_inet_ntoa
0x1800822eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800822f2  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800822f9  mov     edx, 1Eh
0x1800822fe  mov     [rsp+0C0h+dwDesiredAccess], ebx
0x180082302  mov     r9, rax
0x180082305  mov     rcx, [rcx+10h]
0x180082309  call    WPP_SF_sd
0x18008230e  mov     rcx, cs:WPP_GLOBAL_Control
0x180082315  lea     rbx, WPP_GLOBAL_Control
0x18008231c  cmp     rcx, rbx
0x18008231f  jz      loc_1800823D3
0x180082325  test    byte ptr [rcx+1Ch], 1
0x180082329  jz      short loc_18008237B
0x18008232b  cmp     byte ptr [rcx+19h], 4
0x18008232f  jb      short loc_18008237B
0x180082331  movzx   ecx, [rbp+37h+arg_40]; netshort
0x180082338  call    cs:__imp_ntohs
0x18008233e  mov     ecx, dword ptr [rbp+37h+arg_38.S_un]; in
0x180082341  movzx   ebx, ax
0x180082344  call    cs:__imp_inet_ntoa
0x18008234a  mov     rcx, cs:WPP_GLOBAL_Control
0x180082351  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082358  mov     edx, 1Fh
0x18008235d  mov     [rsp+0C0h+dwDesiredAccess], ebx
0x180082361  mov     r9, rax
0x180082364  mov     rcx, [rcx+10h]
0x180082368  call    WPP_SF_sd
0x18008236d  mov     rcx, cs:WPP_GLOBAL_Control
0x180082374  lea     rbx, WPP_GLOBAL_Control
0x18008237b  cmp     rcx, rbx
0x18008237e  jz      short loc_1800823D3
0x180082380  test    byte ptr [rcx+1Ch], 1
0x180082384  jz      short loc_1800823D3
0x180082386  cmp     byte ptr [rcx+19h], 4
0x18008238a  jb      short loc_1800823D3
0x18008238c  movzx   ecx, r12w; netshort
0x180082390  call    cs:__imp_ntohs
0x180082396  mov     ecx, r13d; in
0x180082399  movzx   ebx, ax
0x18008239c  call    cs:__imp_inet_ntoa
0x1800823a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800823a9  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800823b0  mov     edx, 20h ; ' '
0x1800823b5  mov     [rsp+0C0h+dwDesiredAccess], ebx
0x1800823b9  mov     r9, rax
0x1800823bc  mov     rcx, [rcx+10h]
0x1800823c0  call    WPP_SF_sd
0x1800823c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800823cc  lea     rbx, WPP_GLOBAL_Control
0x1800823d3  mov     r8, [rbp+37h+dwProcessId]; dwProcessId
0x1800823da  mov     [rbp+37h+TargetHandle], 0
0x1800823e2  mov     [rbp+37h+hObject], 0
0x1800823ea  test    r8, r8
0x1800823ed  jz      loc_180082657
0x1800823f3  xor     edx, edx; bInheritHandle
0x1800823f5  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800823f8  call    cs:__imp_OpenProcess
0x1800823fe  mov     rbx, rax
0x180082401  test    rax, rax
0x180082404  jnz     short loc_180082456
0x180082406  mov     rcx, cs:WPP_GLOBAL_Control
0x18008240d  lea     rax, WPP_GLOBAL_Control
0x180082414  cmp     rcx, rax
0x180082417  jz      short loc_18008243B
0x180082419  test    byte ptr [rcx+1Ch], 1
0x18008241d  jz      short loc_18008243B
0x18008241f  cmp     byte ptr [rcx+19h], 2
0x180082423  jb      short loc_18008243B
0x180082425  mov     rcx, [rcx+10h]
0x180082429  lea     edx, [rbx+21h]
0x18008242c  xor     r9d, r9d
0x18008242f  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082436  call    WPP_SF_d
0x18008243b  call    cs:__imp_GetLastError
0x180082441  test    eax, eax
0x180082443  jle     loc_180082777
0x180082449  movzx   eax, ax
0x18008244c  or      eax, 80070000h
0x180082451  jmp     loc_180082777
0x180082456  mov     rdi, [rbp+37h+hSourceHandle]
0x18008245d  test    rdi, rdi
0x180082460  jz      loc_180082518
0x180082466  call    cs:__imp_GetCurrentProcess
0x18008246c  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x180082474  lea     r9, [rbp+37h+TargetHandle]; lpTargetHandle
0x180082478  mov     r8, rax; hTargetProcessHandle
0x18008247b  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x180082483  mov     rdx, rdi; hSourceHandle
0x180082486  mov     [rsp+0C0h+dwDesiredAccess], 0; dwDesiredAccess
0x18008248e  mov     rcx, rbx; hSourceProcessHandle
0x180082491  call    cs:__imp_DuplicateHandle
0x180082497  test    eax, eax
0x180082499  jnz     short loc_1800824E0
0x18008249b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800824a2  lea     rax, WPP_GLOBAL_Control
0x1800824a9  cmp     rcx, rax
0x1800824ac  jz      short loc_1800824D2
0x1800824ae  test    byte ptr [rcx+1Ch], 1
0x1800824b2  jz      short loc_1800824D2
0x1800824b4  cmp     byte ptr [rcx+19h], 2
0x1800824b8  jb      short loc_1800824D2
0x1800824ba  mov     rcx, [rcx+10h]
0x1800824be  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800824c5  mov     edx, 22h ; '"'
0x1800824ca  xor     r9d, r9d
0x1800824cd  call    WPP_SF_d
0x1800824d2  mov     rcx, rbx; hObject
0x1800824d5  call    cs:__imp_CloseHandle
0x1800824db  jmp     loc_18008243B
0x1800824e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800824e7  lea     rax, WPP_GLOBAL_Control
0x1800824ee  cmp     rcx, rax
0x1800824f1  jz      short loc_18008255A
0x1800824f3  test    byte ptr [rcx+1Ch], 1
0x1800824f7  jz      short loc_18008255A
0x1800824f9  cmp     byte ptr [rcx+19h], 4
0x1800824fd  jb      short loc_18008255A
0x1800824ff  mov     r9, [rbp+37h+TargetHandle]
0x180082503  mov     edx, 23h ; '#'
0x180082508  mov     rcx, [rcx+10h]
0x18008250c  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rdi
0x180082511  call    WPP_SF_qq
0x180082516  jmp     short loc_18008254C
0x180082518  mov     rcx, cs:WPP_GLOBAL_Control
0x18008251f  lea     rax, WPP_GLOBAL_Control
0x180082526  cmp     rcx, rax
0x180082529  jz      short loc_18008255A
0x18008252b  test    byte ptr [rcx+1Ch], 1
0x18008252f  jz      short loc_18008255A
0x180082531  cmp     byte ptr [rcx+19h], 4
0x180082535  jb      short loc_18008255A
0x180082537  mov     rcx, [rcx+10h]
0x18008253b  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082542  mov     edx, 24h ; '$'
0x180082547  call    WPP_SF_
0x18008254c  mov     rcx, cs:WPP_GLOBAL_Control
0x180082553  lea     rax, WPP_GLOBAL_Control
0x18008255a  mov     rdi, [rbp+37h+arg_70]
0x180082561  test    rdi, rdi
0x180082564  jz      loc_180082626
0x18008256a  call    cs:__imp_GetCurrentProcess
0x180082570  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x180082578  lea     r9, [rbp+37h+hObject]; lpTargetHandle
0x18008257c  mov     r8, rax; hTargetProcessHandle
0x18008257f  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x180082587  mov     rdx, rdi; hSourceHandle
0x18008258a  mov     [rsp+0C0h+dwDesiredAccess], 0; dwDesiredAccess
0x180082592  mov     rcx, rbx; hSourceProcessHandle
0x180082595  call    cs:__imp_DuplicateHandle
0x18008259b  test    eax, eax
0x18008259d  jnz     short loc_1800825EE
0x18008259f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800825a6  lea     rax, WPP_GLOBAL_Control
0x1800825ad  cmp     rcx, rax
0x1800825b0  jz      short loc_1800825D6
0x1800825b2  test    byte ptr [rcx+1Ch], 1
0x1800825b6  jz      short loc_1800825D6
0x1800825b8  cmp     byte ptr [rcx+19h], 2
0x1800825bc  jb      short loc_1800825D6
0x1800825be  mov     rcx, [rcx+10h]
0x1800825c2  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800825c9  mov     edx, 25h ; '%'
0x1800825ce  xor     r9d, r9d
0x1800825d1  call    WPP_SF_d
0x1800825d6  mov     rcx, [rbp+37h+TargetHandle]; hObject
0x1800825da  test    rcx, rcx
0x1800825dd  jz      loc_1800824D2
0x1800825e3  call    cs:__imp_CloseHandle
0x1800825e9  jmp     loc_1800824D2
0x1800825ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800825f5  lea     rax, WPP_GLOBAL_Control
0x1800825fc  cmp     rcx, rax
0x1800825ff  jz      short loc_18008264C
0x180082601  test    byte ptr [rcx+1Ch], 1
0x180082605  jz      short loc_18008264C
0x180082607  cmp     byte ptr [rcx+19h], 4
0x18008260b  jb      short loc_18008264C
0x18008260d  mov     r9, [rbp+37h+hObject]
0x180082611  mov     edx, 26h ; '&'
0x180082616  mov     rcx, [rcx+10h]
0x18008261a  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rdi
0x18008261f  call    WPP_SF_qq
0x180082624  jmp     short loc_18008264C
0x180082626  cmp     rcx, rax
0x180082629  jz      short loc_18008264C
0x18008262b  test    byte ptr [rcx+1Ch], 1
0x18008262f  jz      short loc_18008264C
0x180082631  cmp     byte ptr [rcx+19h], 4
0x180082635  jb      short loc_18008264C
0x180082637  mov     rcx, [rcx+10h]
0x18008263b  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082642  mov     edx, 27h ; '''
0x180082647  call    WPP_SF_
0x18008264c  mov     rcx, rbx; hObject
0x18008264f  call    cs:__imp_CloseHandle
0x180082655  jmp     short loc_18008267D
0x180082657  cmp     rcx, rbx
0x18008265a  jz      short loc_18008267D
0x18008265c  test    byte ptr [rcx+1Ch], 1
0x180082660  jz      short loc_18008267D
0x180082662  cmp     byte ptr [rcx+19h], 4
0x180082666  jb      short loc_18008267D
0x180082668  mov     rcx, [rcx+10h]
0x18008266c  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180082673  mov     edx, 28h ; '('
0x180082678  call    WPP_SF_
0x18008267d  mov     rbx, [rbp+37h+TargetHandle]
0x180082681  mov     rdi, [rbp+37h+hObject]
0x180082685  cmp     sil, 1
  ... truncated ...
```
