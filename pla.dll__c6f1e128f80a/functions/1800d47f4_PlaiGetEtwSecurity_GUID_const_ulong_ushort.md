# PlaiGetEtwSecurity(_GUID const *,ulong,ushort * *)

- ea: `0x1800d47f4`
- end: `0x1800d4bc6`
- name: `?PlaiGetEtwSecurity@@YAJPEBU_GUID@@KPEAPEAG@Z`
- size: `978`
- prototype: `int(const struct _GUID *, unsigned int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800018b0`
- `0x1800eef90`
- `0x1800fdf10`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x18002b3a0`
- `0x1800d47f4`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d4b94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d4b94`
- `api-ms-win-eventing-controller-l1-1-0!EventAccessQuery` at `0x1800d4885`
- `api-ms-win-eventing-controller-l1-1-0!EventAccessQuery` at `0x1800d4885`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800d492f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800d492f`

## string_xrefs

- `0x1800d49f3`: `PlaiGetEtwSecurity`
- `0x1800d4b4a`: `PlaiGetEtwSecurity`

## pseudocode

```c
__int64 __fastcall PlaiGetEtwSecurity(const struct _GUID *a1, SECURITY_INFORMATION a2, unsigned __int16 **a3)
{
  GUID v3; // xmm0
  void *v6; // rdi
  void *v7; // rax
  ULONG v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  int *v12; // r9
  int *v13; // rcx
  const char *v14; // rdx
  int v15; // r8d
  unsigned __int16 *v16; // rax
  __int64 v17; // rax
  DWORD LastError; // eax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  int StringSecurityDescriptorLen; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+78h] [rbp-88h] BYREF
  ULONG BufferSize; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  GUID Guid; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v29[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v30[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v31[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v32[64]; // [rsp+220h] [rbp+120h] BYREF

  v3 = *a1;
  BufferSize = 1024;
  StringSecurityDescriptor = 0;
  v6 = 0;
  Guid = v3;
  while ( 1 )
  {
    if ( v6 )
      PlaiFree(v6, 1);
    v7 = PlaiAlloc(BufferSize, 1, 0, qword_180147320, StringSecurityDescriptorLen);
    v6 = v7;
    if ( !v7 )
      break;
    v8 = EventAccessQuery(&Guid, v7, &BufferSize);
    v9 = PlaiHResultFromWin32(v8);
    v10 = v9;
    if ( v9 != -2147024774 )
    {
      if ( v9 < 0 )
      {
        v24 = 0;
        v25 = v9;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v29, 0x4000000000000800uLL);
          v11 = -1;
          do
            ++v11;
          while ( v29[v11] );
          v12 = &v25;
          v13 = &v24;
LABEL_22:
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            v12,
            4,
            qword_180147320,
            1,
            v13,
            4,
            "PlaiGetEtwSecurity",
            19);
        }
LABEL_23:
        PlaiFree(v6, 1);
        goto LABEL_37;
      }
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v6, 1u, a2, &StringSecurityDescriptor, 0) )
      {
        v10 = 0;
LABEL_15:
        v16 = PlaiAllocStringEx(StringSecurityDescriptor, v14, v15);
        *a3 = v16;
        if ( v16 )
          goto LABEL_23;
        v10 = -2147024882;
        v24 = -2147024882;
        v25 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_23;
        }
        PlaiWhoAmI(v31, 0x4000000000000800uLL);
        v17 = -1;
        do
          ++v17;
        while ( v31[v17] );
      }
      else
      {
        LastError = GetLastError();
        v19 = PlaiHResultFromWin32(LastError);
        v10 = v19;
        if ( v19 >= 0 )
          goto LABEL_15;
        v25 = 0;
        v24 = v19;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_23;
        }
        PlaiWhoAmI(v30, 0x4000000000000800uLL);
        v20 = -1;
        do
          ++v20;
        while ( v30[v20] );
      }
      v12 = &v24;
      v13 = &v25;
      goto LABEL_22;
    }
  }
  v10 = -2147024882;
  v24 = -2147024882;
  v25 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v32, 0x4000000000000800uLL);
    v21 = -1;
    do
      ++v21;
    while ( v32[v21] );
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v24, 4, qword_180147320, 1, &v25, 4, "PlaiGetEtwSecurity", 19);
  }
LABEL_37:
  if ( StringSecurityDescriptor )
    LocalFree(StringSecurityDescriptor);
  return v10;
}

```

## disassembly

```asm
0x1800d47f4  mov     [rsp-8+arg_18], rbx
0x1800d47f9  push    rbp
0x1800d47fa  push    rsi
0x1800d47fb  push    rdi
0x1800d47fc  push    r12
0x1800d47fe  push    r13
0x1800d4800  push    r14
0x1800d4802  push    r15
0x1800d4804  lea     rbp, [rsp-1B0h]
0x1800d480c  sub     rsp, 2B0h
0x1800d4813  mov     rax, cs:__security_cookie
0x1800d481a  xor     rax, rsp
0x1800d481d  mov     [rbp+1E0h+var_40], rax
0x1800d4824  movups  xmm0, xmmword ptr [rcx]
0x1800d4827  xor     r15d, r15d
0x1800d482a  mov     [rbp+1E0h+BufferSize], 400h
0x1800d4831  mov     r14, r8
0x1800d4834  mov     [rbp+1E0h+StringSecurityDescriptor], r15
0x1800d4838  mov     esi, edx
0x1800d483a  lea     r13, qword_180147320
0x1800d4841  mov     edi, r15d
0x1800d4844  lea     r12d, [r15+1]
0x1800d4848  movdqu  xmmword ptr [rbp+1E0h+Guid.Data1], xmm0
0x1800d484d  test    rdi, rdi
0x1800d4850  jz      short loc_1800D485D
0x1800d4852  mov     edx, r12d; int
0x1800d4855  mov     rcx, rdi; lpMem
0x1800d4858  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800d485d  mov     ecx, [rbp+1E0h+BufferSize]; dwBytes
0x1800d4860  mov     r9, r13; char *
0x1800d4863  xor     r8d, r8d; int
0x1800d4866  mov     edx, r12d; int
0x1800d4869  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800d486e  mov     rdi, rax
0x1800d4871  test    rax, rax
0x1800d4874  jz      loc_1800D4AB3
0x1800d487a  lea     r8, [rbp+1E0h+BufferSize]; BufferSize
0x1800d487e  mov     rdx, rax; Buffer
0x1800d4881  lea     rcx, [rbp+1E0h+Guid]; Guid
0x1800d4885  call    cs:__imp_EventAccessQuery
0x1800d488b  mov     ecx, eax; unsigned int
0x1800d488d  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800d4892  mov     ebx, eax
0x1800d4894  cmp     eax, 8007007Ah
0x1800d4899  jz      short loc_1800D484D
0x1800d489b  test    eax, eax
0x1800d489d  jns     short loc_1800D491D
0x1800d489f  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800d48a6  mov     [rsp+2E0h+var_270], r15d
0x1800d48ab  mov     [rsp+2E0h+var_268], eax
0x1800d48af  jz      loc_1800D4A2D
0x1800d48b5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d48bf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d48c6  jz      loc_1800D4A2D
0x1800d48cc  mov     rax, cs:qword_180169748
0x1800d48d3  and     rax, rdx
0x1800d48d6  cmp     cs:qword_180169748, rax
0x1800d48dd  jnz     loc_1800D4A2D
0x1800d48e3  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x1800d48e7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d48ec  lea     rcx, [rbp+1E0h+var_240]
0x1800d48f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d48f4  inc     rax
0x1800d48f7  cmp     [rcx+rax*2], r15w
0x1800d48fc  jnz     short loc_1800D48F4
0x1800d48fe  lea     ecx, [rax+rax]
0x1800d4901  add     rcx, 2
0x1800d4905  lea     rax, [rbp+1E0h+var_240]
0x1800d4909  mov     [rsp+2E0h+var_280], rcx
0x1800d490e  lea     r9, [rsp+2E0h+var_268]
0x1800d4913  lea     rcx, [rsp+2E0h+var_270]
0x1800d4918  jmp     loc_1800D49DE
0x1800d491d  lea     r9, [rbp+1E0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800d4921  mov     [rsp+2E0h+StringSecurityDescriptorLen], r15; StringSecurityDescriptorLen
0x1800d4926  mov     r8d, esi; SecurityInformation
0x1800d4929  mov     edx, r12d; RequestedStringSDRevision
0x1800d492c  mov     rcx, rdi; SecurityDescriptor
0x1800d492f  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800d4935  test    eax, eax
0x1800d4937  jz      loc_1800D4A3D
0x1800d493d  mov     ebx, r15d
0x1800d4940  mov     rcx, [rbp+1E0h+StringSecurityDescriptor]; unsigned __int16 *
0x1800d4944  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800d4949  mov     [r14], rax
0x1800d494c  test    rax, rax
0x1800d494f  jnz     loc_1800D4A2D
0x1800d4955  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800d495c  mov     eax, 8007000Eh
0x1800d4961  mov     ebx, eax
0x1800d4963  mov     [rsp+2E0h+var_270], eax
0x1800d4967  mov     [rsp+2E0h+var_268], r15d
0x1800d496c  jz      loc_1800D4A2D
0x1800d4972  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d497c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d4983  jz      loc_1800D4A2D
0x1800d4989  mov     rax, cs:qword_180169748
0x1800d4990  and     rax, rdx
0x1800d4993  cmp     cs:qword_180169748, rax
0x1800d499a  jnz     loc_1800D4A2D
0x1800d49a0  lea     rcx, [rbp+1E0h+var_140]; unsigned __int16 *
0x1800d49a7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d49ac  lea     rcx, [rbp+1E0h+var_140]
0x1800d49b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d49b7  inc     rax
0x1800d49ba  cmp     [rcx+rax*2], r15w
0x1800d49bf  jnz     short loc_1800D49B7
0x1800d49c1  lea     ecx, [rax+rax]
0x1800d49c4  lea     rax, [rbp+1E0h+var_140]
0x1800d49cb  add     rcx, 2
0x1800d49cf  lea     r9, [rsp+2E0h+var_270]
0x1800d49d4  mov     [rsp+2E0h+var_280], rcx
0x1800d49d9  lea     rcx, [rsp+2E0h+var_268]
0x1800d49de  mov     [rsp+2E0h+var_288], rax
0x1800d49e3  lea     rdx, PLA_EVENT_ERROR
0x1800d49ea  mov     [rsp+2E0h+var_290], 13h
0x1800d49f3  lea     rax, aPlaigetetwsecu; "PlaiGetEtwSecurity"
0x1800d49fa  mov     [rsp+2E0h+var_298], rax
0x1800d49ff  mov     eax, 4
0x1800d4a04  mov     [rsp+2E0h+var_2A0], rax
0x1800d4a09  mov     [rsp+2E0h+var_2A8], rcx
0x1800d4a0e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d4a15  mov     [rsp+2E0h+var_2B0], r12
0x1800d4a1a  mov     [rsp+2E0h+var_2B8], r13
0x1800d4a1f  lea     r8d, [rax+1]
0x1800d4a23  mov     [rsp+2E0h+StringSecurityDescriptorLen], rax
0x1800d4a28  call    EventingWriteEvent
0x1800d4a2d  mov     edx, r12d; int
0x1800d4a30  mov     rcx, rdi; lpMem
0x1800d4a33  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800d4a38  jmp     loc_1800D4B8B
0x1800d4a3d  call    cs:__imp_GetLastError
0x1800d4a43  mov     ecx, eax; unsigned int
0x1800d4a45  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800d4a4a  mov     ebx, eax
0x1800d4a4c  test    eax, eax
0x1800d4a4e  jns     loc_1800D4940
0x1800d4a54  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800d4a5b  mov     [rsp+2E0h+var_268], r15d
0x1800d4a60  mov     [rsp+2E0h+var_270], eax
0x1800d4a64  jz      short loc_1800D4A2D
0x1800d4a66  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d4a70  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d4a77  jz      short loc_1800D4A2D
0x1800d4a79  mov     rax, cs:qword_180169748
0x1800d4a80  and     rax, rdx
0x1800d4a83  cmp     cs:qword_180169748, rax
0x1800d4a8a  jnz     short loc_1800D4A2D
0x1800d4a8c  lea     rcx, [rbp+1E0h+var_1C0]; unsigned __int16 *
0x1800d4a90  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d4a95  lea     rcx, [rbp+1E0h+var_1C0]
0x1800d4a99  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d4a9d  inc     rax
0x1800d4aa0  cmp     [rcx+rax*2], r15w
0x1800d4aa5  jnz     short loc_1800D4A9D
0x1800d4aa7  lea     ecx, [rax+rax]
0x1800d4aaa  lea     rax, [rbp+1E0h+var_1C0]
0x1800d4aae  jmp     loc_1800D49CB
0x1800d4ab3  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800d4aba  mov     eax, 8007000Eh
0x1800d4abf  mov     ebx, eax
0x1800d4ac1  mov     [rsp+2E0h+var_270], eax
0x1800d4ac5  mov     [rsp+2E0h+var_268], r15d
0x1800d4aca  jz      loc_1800D4B8B
0x1800d4ad0  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d4ada  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d4ae1  jz      loc_1800D4B8B
0x1800d4ae7  mov     rax, cs:qword_180169748
0x1800d4aee  and     rax, rdx
0x1800d4af1  cmp     cs:qword_180169748, rax
0x1800d4af8  jnz     loc_1800D4B8B
0x1800d4afe  lea     rcx, [rbp+1E0h+var_C0]; unsigned __int16 *
0x1800d4b05  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d4b0a  lea     rcx, [rbp+1E0h+var_C0]
0x1800d4b11  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d4b15  inc     rax
0x1800d4b18  cmp     [rcx+rax*2], r15w
0x1800d4b1d  jnz     short loc_1800D4B15
0x1800d4b1f  lea     ecx, [rax+rax]
0x1800d4b22  add     rcx, 2
0x1800d4b26  lea     rax, [rbp+1E0h+var_C0]
0x1800d4b2d  mov     [rsp+2E0h+var_280], rcx
0x1800d4b32  lea     r9, [rsp+2E0h+var_270]
0x1800d4b37  mov     [rsp+2E0h+var_288], rax
0x1800d4b3c  lea     rcx, [rsp+2E0h+var_268]
0x1800d4b41  mov     [rsp+2E0h+var_290], 13h
0x1800d4b4a  lea     rax, aPlaigetetwsecu; "PlaiGetEtwSecurity"
0x1800d4b51  mov     [rsp+2E0h+var_298], rax
0x1800d4b56  lea     rdx, PLA_EVENT_ERROR
0x1800d4b5d  mov     eax, 4
0x1800d4b62  mov     [rsp+2E0h+var_2A0], rax
0x1800d4b67  mov     [rsp+2E0h+var_2A8], rcx
0x1800d4b6c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d4b73  mov     [rsp+2E0h+var_2B0], r12
0x1800d4b78  mov     [rsp+2E0h+var_2B8], r13
0x1800d4b7d  lea     r8d, [rax+1]
0x1800d4b81  mov     [rsp+2E0h+StringSecurityDescriptorLen], rax
0x1800d4b86  call    EventingWriteEvent
0x1800d4b8b  mov     rcx, [rbp+1E0h+StringSecurityDescriptor]; hMem
0x1800d4b8f  test    rcx, rcx
0x1800d4b92  jz      short loc_1800D4B9A
0x1800d4b94  call    cs:__imp_LocalFree
0x1800d4b9a  mov     eax, ebx
0x1800d4b9c  mov     rcx, [rbp+1E0h+var_40]
0x1800d4ba3  xor     rcx, rsp; StackCookie
0x1800d4ba6  call    __security_check_cookie
0x1800d4bab  mov     rbx, [rsp+2E0h+arg_18]
0x1800d4bb3  add     rsp, 2B0h
0x1800d4bba  pop     r15
0x1800d4bbc  pop     r14
0x1800d4bbe  pop     r13
0x1800d4bc0  pop     r12
0x1800d4bc2  pop     rdi
0x1800d4bc3  pop     rsi
0x1800d4bc4  pop     rbp
0x1800d4bc5  retn
```
