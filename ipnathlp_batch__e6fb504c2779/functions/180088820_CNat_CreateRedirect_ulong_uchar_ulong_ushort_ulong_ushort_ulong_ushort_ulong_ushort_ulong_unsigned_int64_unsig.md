# CNat::CreateRedirect(ulong,uchar,ulong,ushort,ulong,ushort,ulong,ushort,ulong,ushort,ulong,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180088820`
- end: `0x180088ea5`
- name: `?CreateRedirect@CNat@@UEAAJKEKGKGKGKGK_K00@Z`
- size: `1669`
- prototype: `__int64 __usercall@<rax>(CNat *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int8@<r8b>, unsigned int@<r9d>, unsigned __int16, struct in_addr in, unsigned __int16, struct in_addr, unsigned __int16, struct in_addr, unsigned __int16, unsigned int, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180013340`
- `0x180013650`
- `0x180033e0c`
- `0x18005b5f0`
- `0x180088820`
- `0x180089518`
- `0x180089b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180088b42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180088c58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180088b42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180088c58`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180088b73`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180088c89`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180088b73`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180088c89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088cdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088d4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088cdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088d4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e2f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180088ac8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180088ac8`
- `WS2_32!__imp_inet_ntoa` at `0x18008892f`
- `WS2_32!__imp_inet_ntoa` at `0x180088997`
- `WS2_32!__imp_inet_ntoa` at `0x180088a02`
- `WS2_32!__imp_inet_ntoa` at `0x180088a66`
- `WS2_32!__imp_inet_ntoa` at `0x18008892f`
- `WS2_32!__imp_inet_ntoa` at `0x180088997`
- `WS2_32!__imp_inet_ntoa` at `0x180088a02`
- `WS2_32!__imp_inet_ntoa` at `0x180088a66`
- `WS2_32!__imp_ntohs` at `0x18008891e`
- `WS2_32!__imp_ntohs` at `0x180088985`
- `WS2_32!__imp_ntohs` at `0x1800889f0`
- `WS2_32!__imp_ntohs` at `0x180088a54`
- `WS2_32!__imp_ntohs` at `0x18008891e`
- `WS2_32!__imp_ntohs` at `0x180088985`
- `WS2_32!__imp_ntohs` at `0x1800889f0`
- `WS2_32!__imp_ntohs` at `0x180088a54`

## pseudocode

```c
signed int __fastcall CNat::CreateRedirect(
        void **this,
        int a2,
        unsigned __int8 a3,
        int a4,
        u_short a5,
        struct in_addr in,
        unsigned __int16 a7,
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
0x180088820  mov     rax, rsp
0x180088823  mov     [rax+8], rbx
0x180088827  mov     [rax+20h], r9d
0x18008882b  mov     [rax+10h], edx
0x18008882e  push    rbp
0x18008882f  push    rsi
0x180088830  push    rdi
0x180088831  push    r12
0x180088833  push    r13
0x180088835  push    r14
0x180088837  push    r15
0x180088839  lea     rbp, [rax-3Fh]
0x18008883d  sub     rsp, 90h
0x180088844  mov     edi, r9d
0x180088847  movzx   esi, r8b
0x18008884b  mov     r15, rcx
0x18008884e  mov     rcx, cs:WPP_GLOBAL_Control
0x180088855  lea     rbx, WPP_GLOBAL_Control
0x18008885c  mov     r14b, 6
0x18008885f  cmp     rcx, rbx
0x180088862  jz      short loc_180088885
0x180088864  test    byte ptr [rcx+1Ch], 1
0x180088868  jz      short loc_180088885
0x18008886a  cmp     [rcx+19h], r14b
0x18008886e  jb      short loc_180088885
0x180088870  mov     rcx, [rcx+10h]
0x180088874  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x18008887b  mov     edx, 1Bh
0x180088880  call    WPP_SF_
0x180088885  mov     rcx, r15; this
0x180088888  call    ?IsClientAllowedToCallUs@CNat@@AEAA_NXZ; CNat::IsClientAllowedToCallUs(void)
0x18008888d  test    al, al
0x18008888f  jnz     short loc_18008889B
0x180088891  mov     eax, 80070005h
0x180088896  jmp     loc_180088E89
0x18008889b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800888a2  mov     edx, 11h
0x1800888a7  movzx   r12d, [rbp+37h+arg_50]
0x1800888af  mov     r13d, dword ptr [rbp+37h+arg_48.S_un]
0x1800888b6  cmp     rcx, rbx
0x1800888b9  jz      loc_180088AA3
0x1800888bf  test    byte ptr [rcx+1Ch], 1
0x1800888c3  jz      short loc_180088905
0x1800888c5  cmp     byte ptr [rcx+19h], 4
0x1800888c9  jb      short loc_180088905
0x1800888cb  cmp     sil, 1
0x1800888cf  jnz     short loc_1800888D6
0x1800888d1  mov     al, r14b
0x1800888d4  jmp     short loc_1800888DF
0x1800888d6  cmp     sil, 2
0x1800888da  mov     eax, esi
0x1800888dc  cmovz   eax, edx
0x1800888df  mov     rcx, [rcx+10h]
0x1800888e3  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800888ea  movzx   eax, al
0x1800888ed  mov     r9d, esi
0x1800888f0  mov     edx, 1Ch
0x1800888f5  mov     [rsp+0C0h+dwDesiredAccess], eax
0x1800888f9  call    WPP_SF_dd
0x1800888fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180088905  cmp     rcx, rbx
0x180088908  jz      loc_180088AA3
0x18008890e  test    byte ptr [rcx+1Ch], 1
0x180088912  jz      short loc_18008896C
0x180088914  cmp     byte ptr [rcx+19h], 4
0x180088918  jb      short loc_18008896C
0x18008891a  movzx   ecx, [rbp+37h+arg_20]; netshort
0x18008891e  call    cs:__imp_ntohs
0x180088925  nop     dword ptr [rax+rax+00h]
0x18008892a  mov     ecx, edi; in
0x18008892c  movzx   ebx, ax
0x18008892f  call    cs:__imp_inet_ntoa
0x180088936  nop     dword ptr [rax+rax+00h]
0x18008893b  mov     rcx, cs:WPP_GLOBAL_Control
0x180088942  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180088949  mov     edx, 1Dh
0x18008894e  mov     [rsp+0C0h+dwDesiredAccess], ebx
0x180088952  mov     r9, rax
0x180088955  mov     rcx, [rcx+10h]
0x180088959  call    WPP_SF_sd
0x18008895e  mov     rcx, cs:WPP_GLOBAL_Control
0x180088965  lea     rbx, WPP_GLOBAL_Control
0x18008896c  cmp     rcx, rbx
0x18008896f  jz      loc_180088AA3
0x180088975  test    byte ptr [rcx+1Ch], 1
0x180088979  jz      short loc_1800889D4
0x18008897b  cmp     byte ptr [rcx+19h], 4
0x18008897f  jb      short loc_1800889D4
0x180088981  movzx   ecx, [rbp+37h+arg_30]; netshort
0x180088985  call    cs:__imp_ntohs
0x18008898c  nop     dword ptr [rax+rax+00h]
0x180088991  mov     ecx, dword ptr [rbp+37h+in.S_un]; in
0x180088994  movzx   ebx, ax
0x180088997  call    cs:__imp_inet_ntoa
0x18008899e  nop     dword ptr [rax+rax+00h]
0x1800889a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800889aa  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x1800889b1  mov     edx, 1Eh
0x1800889b6  mov     [rsp+0C0h+dwDesiredAccess], ebx
0x1800889ba  mov     r9, rax
0x1800889bd  mov     rcx, [rcx+10h]
0x1800889c1  call    WPP_SF_sd
0x1800889c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800889cd  lea     rbx, WPP_GLOBAL_Control
0x1800889d4  cmp     rcx, rbx
0x1800889d7  jz      loc_180088AA3
0x1800889dd  test    byte ptr [rcx+1Ch], 1
0x1800889e1  jz      short loc_180088A3F
0x1800889e3  cmp     byte ptr [rcx+19h], 4
0x1800889e7  jb      short loc_180088A3F
0x1800889e9  movzx   ecx, [rbp+37h+arg_40]; netshort
0x1800889f0  call    cs:__imp_ntohs
0x1800889f7  nop     dword ptr [rax+rax+00h]
0x1800889fc  mov     ecx, dword ptr [rbp+37h+arg_38.S_un]; in
0x1800889ff  movzx   ebx, ax
0x180088a02  call    cs:__imp_inet_ntoa
0x180088a09  nop     dword ptr [rax+rax+00h]
0x180088a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180088a15  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180088a1c  mov     edx, 1Fh
0x180088a21  mov     [rsp+0C0h+dwDesiredAccess], ebx
0x180088a25  mov     r9, rax
0x180088a28  mov     rcx, [rcx+10h]
0x180088a2c  call    WPP_SF_sd
0x180088a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180088a38  lea     rbx, WPP_GLOBAL_Control
0x180088a3f  cmp     rcx, rbx
0x180088a42  jz      short loc_180088AA3
0x180088a44  test    byte ptr [rcx+1Ch], 1
0x180088a48  jz      short loc_180088AA3
0x180088a4a  cmp     byte ptr [rcx+19h], 4
0x180088a4e  jb      short loc_180088AA3
0x180088a50  movzx   ecx, r12w; netshort
0x180088a54  call    cs:__imp_ntohs
0x180088a5b  nop     dword ptr [rax+rax+00h]
0x180088a60  mov     ecx, r13d; in
0x180088a63  movzx   ebx, ax
0x180088a66  call    cs:__imp_inet_ntoa
0x180088a6d  nop     dword ptr [rax+rax+00h]
0x180088a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180088a79  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180088a80  mov     edx, 20h ; ' '
0x180088a85  mov     [rsp+0C0h+dwDesiredAccess], ebx
0x180088a89  mov     r9, rax
0x180088a8c  mov     rcx, [rcx+10h]
0x180088a90  call    WPP_SF_sd
0x180088a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180088a9c  lea     rbx, WPP_GLOBAL_Control
0x180088aa3  mov     r8, [rbp+37h+dwProcessId]; dwProcessId
0x180088aaa  mov     [rbp+37h+TargetHandle], 0
0x180088ab2  mov     [rbp+37h+hObject], 0
0x180088aba  test    r8, r8
0x180088abd  jz      loc_180088D5D
0x180088ac3  xor     edx, edx; bInheritHandle
0x180088ac5  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180088ac8  call    cs:__imp_OpenProcess
0x180088acf  nop     dword ptr [rax+rax+00h]
0x180088ad4  mov     rbx, rax
0x180088ad7  test    rax, rax
0x180088ada  jnz     short loc_180088B32
0x180088adc  mov     rcx, cs:WPP_GLOBAL_Control
0x180088ae3  lea     rax, WPP_GLOBAL_Control
0x180088aea  cmp     rcx, rax
0x180088aed  jz      short loc_180088B11
0x180088aef  test    byte ptr [rcx+1Ch], 1
0x180088af3  jz      short loc_180088B11
0x180088af5  cmp     byte ptr [rcx+19h], 2
0x180088af9  jb      short loc_180088B11
0x180088afb  mov     rcx, [rcx+10h]
0x180088aff  lea     edx, [rbx+21h]
0x180088b02  xor     r9d, r9d
0x180088b05  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180088b0c  call    WPP_SF_d
0x180088b11  call    cs:__imp_GetLastError
0x180088b18  nop     dword ptr [rax+rax+00h]
0x180088b1d  test    eax, eax
0x180088b1f  jle     loc_180088E89
0x180088b25  movzx   eax, ax
0x180088b28  or      eax, 80070000h
0x180088b2d  jmp     loc_180088E89
0x180088b32  mov     rdi, [rbp+37h+hSourceHandle]
0x180088b39  test    rdi, rdi
0x180088b3c  jz      loc_180088C06
0x180088b42  call    cs:__imp_GetCurrentProcess
0x180088b49  nop     dword ptr [rax+rax+00h]
0x180088b4e  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x180088b56  lea     r9, [rbp+37h+TargetHandle]; lpTargetHandle
0x180088b5a  mov     r8, rax; hTargetProcessHandle
0x180088b5d  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x180088b65  mov     rdx, rdi; hSourceHandle
0x180088b68  mov     [rsp+0C0h+dwDesiredAccess], 0; dwDesiredAccess
0x180088b70  mov     rcx, rbx; hSourceProcessHandle
0x180088b73  call    cs:__imp_DuplicateHandle
0x180088b7a  nop     dword ptr [rax+rax+00h]
0x180088b7f  test    eax, eax
0x180088b81  jnz     short loc_180088BCE
0x180088b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180088b8a  lea     rax, WPP_GLOBAL_Control
0x180088b91  cmp     rcx, rax
0x180088b94  jz      short loc_180088BBA
0x180088b96  test    byte ptr [rcx+1Ch], 1
0x180088b9a  jz      short loc_180088BBA
0x180088b9c  cmp     byte ptr [rcx+19h], 2
0x180088ba0  jb      short loc_180088BBA
0x180088ba2  mov     rcx, [rcx+10h]
0x180088ba6  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180088bad  mov     edx, 22h ; '"'
0x180088bb2  xor     r9d, r9d
0x180088bb5  call    WPP_SF_d
0x180088bba  mov     rcx, rbx; hObject
0x180088bbd  call    cs:__imp_CloseHandle
0x180088bc4  nop     dword ptr [rax+rax+00h]
0x180088bc9  jmp     loc_180088B11
0x180088bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180088bd5  lea     rax, WPP_GLOBAL_Control
0x180088bdc  cmp     rcx, rax
0x180088bdf  jz      short loc_180088C48
0x180088be1  test    byte ptr [rcx+1Ch], 1
0x180088be5  jz      short loc_180088C48
0x180088be7  cmp     byte ptr [rcx+19h], 4
0x180088beb  jb      short loc_180088C48
0x180088bed  mov     r9, [rbp+37h+TargetHandle]
0x180088bf1  mov     edx, 23h ; '#'
0x180088bf6  mov     rcx, [rcx+10h]
0x180088bfa  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rdi
0x180088bff  call    WPP_SF_qq
0x180088c04  jmp     short loc_180088C3A
0x180088c06  mov     rcx, cs:WPP_GLOBAL_Control
0x180088c0d  lea     rax, WPP_GLOBAL_Control
0x180088c14  cmp     rcx, rax
0x180088c17  jz      short loc_180088C48
0x180088c19  test    byte ptr [rcx+1Ch], 1
0x180088c1d  jz      short loc_180088C48
0x180088c1f  cmp     byte ptr [rcx+19h], 4
0x180088c23  jb      short loc_180088C48
0x180088c25  mov     rcx, [rcx+10h]
0x180088c29  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180088c30  mov     edx, 24h ; '$'
0x180088c35  call    WPP_SF_
0x180088c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180088c41  lea     rax, WPP_GLOBAL_Control
0x180088c48  mov     rdi, [rbp+37h+arg_70]
0x180088c4f  test    rdi, rdi
0x180088c52  jz      loc_180088D26
0x180088c58  call    cs:__imp_GetCurrentProcess
0x180088c5f  nop     dword ptr [rax+rax+00h]
0x180088c64  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x180088c6c  lea     r9, [rbp+37h+hObject]; lpTargetHandle
0x180088c70  mov     r8, rax; hTargetProcessHandle
0x180088c73  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x180088c7b  mov     rdx, rdi; hSourceHandle
0x180088c7e  mov     [rsp+0C0h+dwDesiredAccess], 0; dwDesiredAccess
0x180088c86  mov     rcx, rbx; hSourceProcessHandle
0x180088c89  call    cs:__imp_DuplicateHandle
0x180088c90  nop     dword ptr [rax+rax+00h]
0x180088c95  test    eax, eax
0x180088c97  jnz     short loc_180088CEE
0x180088c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180088ca0  lea     rax, WPP_GLOBAL_Control
0x180088ca7  cmp     rcx, rax
0x180088caa  jz      short loc_180088CD0
0x180088cac  test    byte ptr [rcx+1Ch], 1
0x180088cb0  jz      short loc_180088CD0
0x180088cb2  cmp     byte ptr [rcx+19h], 2
0x180088cb6  jb      short loc_180088CD0
0x180088cb8  mov     rcx, [rcx+10h]
0x180088cbc  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180088cc3  mov     edx, 25h ; '%'
0x180088cc8  xor     r9d, r9d
0x180088ccb  call    WPP_SF_d
0x180088cd0  mov     rcx, [rbp+37h+TargetHandle]; hObject
0x180088cd4  test    rcx, rcx
0x180088cd7  jz      loc_180088BBA
0x180088cdd  call    cs:__imp_CloseHandle
0x180088ce4  nop     dword ptr [rax+rax+00h]
0x180088ce9  jmp     loc_180088BBA
0x180088cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180088cf5  lea     rax, WPP_GLOBAL_Control
0x180088cfc  cmp     rcx, rax
0x180088cff  jz      short loc_180088D4C
0x180088d01  test    byte ptr [rcx+1Ch], 1
0x180088d05  jz      short loc_180088D4C
0x180088d07  cmp     byte ptr [rcx+19h], 4
0x180088d0b  jb      short loc_180088D4C
0x180088d0d  mov     r9, [rbp+37h+hObject]
0x180088d11  mov     edx, 26h ; '&'
0x180088d16  mov     rcx, [rcx+10h]
0x180088d1a  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rdi
0x180088d1f  call    WPP_SF_qq
0x180088d24  jmp     short loc_180088D4C
0x180088d26  cmp     rcx, rax
0x180088d29  jz      short loc_180088D4C
0x180088d2b  test    byte ptr [rcx+1Ch], 1
0x180088d2f  jz      short loc_180088D4C
0x180088d31  cmp     byte ptr [rcx+19h], 4
0x180088d35  jb      short loc_180088D4C
0x180088d37  mov     rcx, [rcx+10h]
0x180088d3b  lea     r8, WPP_8ab209e1ee763061284517a200f37d51_Traceguids
0x180088d42  mov     edx, 27h ; '''
0x180088d47  call    WPP_SF_
  ... truncated ...
```
