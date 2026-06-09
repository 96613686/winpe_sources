# LsapParseRemoteAdminAllowList(ushort const *,ulong,void * * *,ulong *)

- ea: `0x1800d7b14`
- end: `0x1800d7db8`
- name: `?LsapParseRemoteAdminAllowList@@YAXPEBGKPEAPEAPEAXPEAK@Z`
- size: `676`
- prototype: `void __fastcall(wchar_t *Source, unsigned int, void ***, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d7880`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x18008e360`
- `0x1800b9304`
- `0x1800d7b14`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800d7bf4`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800d7d57`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800d7bf4`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800d7d57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d7bb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d7b94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d7d39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d7b94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d7d39`
- `ntdll!RtlCopySid` at `0x1800d7cea`
- `ntdll!RtlCopySid` at `0x1800d7cea`
- `ntdll!RtlLengthSid` at `0x1800d7cbe`
- `ntdll!RtlLengthSid` at `0x1800d7cbe`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d7b7c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d7ca2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d7b7c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d7ca2`

## pseudocode

```c
void __fastcall LsapParseRemoteAdminAllowList(wchar_t *Source, unsigned int a2, void ***a3, unsigned int *a4)
{
  __int64 v4; // rdi
  unsigned int v6; // esi
  wchar_t *v7; // rbx
  wchar_t *v8; // rbp
  char LastError; // al
  struct _RTL_BALANCED_NODE *v10; // rax
  struct _RTL_BALANCED_NODE *v11; // rbx
  void *v12; // rdx
  unsigned int v13; // edi
  wchar_t *v14; // rbp
  ULONG v15; // r12d
  struct _RTL_BALANCED_NODE *v16; // rax
  struct _RTL_BALANCED_NODE *v17; // r15
  __int64 v18; // rcx
  unsigned int *v19; // r13
  _QWORD *v20; // rax
  __int64 v21; // [rsp+30h] [rbp-48h]
  PSID Sid; // [rsp+80h] [rbp+8h] BYREF
  void ***v23; // [rsp+90h] [rbp+18h]
  unsigned int *v24; // [rsp+98h] [rbp+20h]

  v24 = a4;
  v23 = a3;
  v4 = a2;
  *a3 = 0;
  *a4 = 0;
  v6 = 0;
  v7 = Source;
  v21 = a2;
  v8 = (wchar_t *)((char *)Source + a2);
  if ( Source < v8 )
  {
    do
    {
      if ( !*v7 )
        break;
      Sid = 0;
      if ( ConvertStringSidToSidW(v7, &Sid) )
      {
        LocalFree(Sid);
        ++v6;
      }
      else if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_0e54213bb8d436d71283068defefc09d_Traceguids,
          (_DWORD)v7,
          LastError);
      }
      v7 += wcsnlen(v7, ((unsigned __int64)Source + v4 - (_QWORD)v7) >> 1) + 1;
    }
    while ( v7 < v8 );
    if ( v6 )
    {
      v10 = (struct _RTL_BALANCED_NODE *)LsapAllocate(8LL * v6);
      v11 = v10;
      if ( v10 )
      {
        memset_0(v10, 0, 8LL * v6);
        v13 = 0;
        v14 = Source;
        do
        {
          if ( !*v14 || v13 >= v6 )
            break;
          Sid = 0;
          if ( ConvertStringSidToSidW(v14, &Sid) )
          {
            v15 = RtlLengthSid(Sid);
            v16 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v15);
            v17 = v16;
            if ( v16 )
            {
              RtlCopySid(v15, v16, Sid);
              v18 = v13++;
              v11->Children[v18] = v17;
            }
            else if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0e54213bb8d436d71283068defefc09d_Traceguids, v15);
            }
            LocalFree(Sid);
          }
          v14 += wcsnlen(v14, ((unsigned __int64)Source + v21 - (_QWORD)v14) >> 1) + 1;
        }
        while ( v14 < (wchar_t *)((char *)Source + v21) );
        v19 = v24;
        if ( !v13 )
        {
          LsapSubProv_FreeRoutine(v11, v12);
          v11 = 0;
        }
        v20 = v23;
        *v19 = v13;
        *v20 = v11;
      }
      else if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0e54213bb8d436d71283068defefc09d_Traceguids, v6);
      }
    }
  }
}

```

## disassembly

```asm
0x1800d7b14  mov     [rsp+arg_8], rbx
0x1800d7b19  mov     [rsp+arg_18], r9
0x1800d7b1e  mov     [rsp+arg_10], r8
0x1800d7b23  push    rbp
0x1800d7b24  push    rsi
0x1800d7b25  push    rdi
0x1800d7b26  push    r12
0x1800d7b28  push    r13
0x1800d7b2a  push    r14
0x1800d7b2c  push    r15
0x1800d7b2e  sub     rsp, 40h
0x1800d7b32  xor     r12d, r12d
0x1800d7b35  mov     edi, edx
0x1800d7b37  mov     r14, rcx
0x1800d7b3a  mov     [r8], r12
0x1800d7b3d  mov     [r9], r12d
0x1800d7b40  mov     esi, r12d
0x1800d7b43  mov     rbx, rcx
0x1800d7b46  mov     [rsp+78h+var_48], rdi
0x1800d7b4b  lea     rbp, [rdi+rcx]
0x1800d7b4f  cmp     rcx, rbp
0x1800d7b52  jnb     loc_1800D7D9F
0x1800d7b58  lea     r15, WPP_GLOBAL_Control
0x1800d7b5f  cmp     [rbx], r12w
0x1800d7b63  jz      loc_1800D7C11
0x1800d7b69  lea     rdx, [rsp+78h+Sid]; Sid
0x1800d7b71  mov     [rsp+78h+Sid], r12
0x1800d7b79  mov     rcx, rbx; StringSid
0x1800d7b7c  call    cs:__imp_ConvertStringSidToSidW
0x1800d7b83  nop     dword ptr [rax+rax+00h]
0x1800d7b88  test    eax, eax
0x1800d7b8a  jz      short loc_1800D7BA4
0x1800d7b8c  mov     rcx, [rsp+78h+Sid]; hMem
0x1800d7b94  call    cs:__imp_LocalFree
0x1800d7b9b  nop     dword ptr [rax+rax+00h]
0x1800d7ba0  inc     esi
0x1800d7ba2  jmp     short loc_1800D7BE5
0x1800d7ba4  mov     rax, cs:WPP_GLOBAL_Control
0x1800d7bab  cmp     rax, r15
0x1800d7bae  jz      short loc_1800D7BE5
0x1800d7bb0  test    byte ptr [rax+1Ch], 2
0x1800d7bb4  jz      short loc_1800D7BE5
0x1800d7bb6  call    cs:__imp_GetLastError
0x1800d7bbd  nop     dword ptr [rax+rax+00h]
0x1800d7bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7bc9  lea     r8, WPP_0e54213bb8d436d71283068defefc09d_Traceguids
0x1800d7bd0  mov     edx, 0Fh
0x1800d7bd5  mov     [rsp+78h+var_58], eax
0x1800d7bd9  mov     r9, rbx
0x1800d7bdc  mov     rcx, [rcx+10h]
0x1800d7be0  call    WPP_SF_Sd
0x1800d7be5  mov     rdx, rdi
0x1800d7be8  mov     rcx, rbx; Source
0x1800d7beb  sub     rdx, rbx
0x1800d7bee  add     rdx, r14
0x1800d7bf1  shr     rdx, 1; MaxCount
0x1800d7bf4  call    cs:__imp_wcsnlen
0x1800d7bfb  nop     dword ptr [rax+rax+00h]
0x1800d7c00  lea     rbx, [rbx+rax*2]
0x1800d7c04  add     rbx, 2
0x1800d7c08  cmp     rbx, rbp
0x1800d7c0b  jb      loc_1800D7B5F
0x1800d7c11  test    esi, esi
0x1800d7c13  jz      loc_1800D7D9F
0x1800d7c19  mov     edi, esi
0x1800d7c1b  shl     rdi, 3
0x1800d7c1f  mov     rcx, rdi
0x1800d7c22  call    LsapAllocate
0x1800d7c27  mov     rbx, rax
0x1800d7c2a  test    rax, rax
0x1800d7c2d  jnz     short loc_1800D7C64
0x1800d7c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7c36  cmp     rcx, r15
0x1800d7c39  jz      loc_1800D7D9F
0x1800d7c3f  test    byte ptr [rcx+1Ch], 1
0x1800d7c43  jz      loc_1800D7D9F
0x1800d7c49  mov     rcx, [rcx+10h]
0x1800d7c4d  lea     edx, [rax+10h]
0x1800d7c50  mov     r9d, esi
0x1800d7c53  lea     r8, WPP_0e54213bb8d436d71283068defefc09d_Traceguids
0x1800d7c5a  call    WPP_SF_d
0x1800d7c5f  jmp     loc_1800D7D9F
0x1800d7c64  mov     r8, rdi; Size
0x1800d7c67  xor     edx, edx; Val
0x1800d7c69  mov     rcx, rbx; void *
0x1800d7c6c  call    memset_0
0x1800d7c71  mov     r13, [rsp+78h+var_48]
0x1800d7c76  mov     edi, r12d
0x1800d7c79  mov     rbp, r14
0x1800d7c7c  cmp     [rbp+0], r12w
0x1800d7c81  jz      loc_1800D7D79
0x1800d7c87  cmp     edi, esi
0x1800d7c89  jnb     loc_1800D7D79
0x1800d7c8f  lea     rdx, [rsp+78h+Sid]; Sid
0x1800d7c97  mov     [rsp+78h+Sid], r12
0x1800d7c9f  mov     rcx, rbp; StringSid
0x1800d7ca2  call    cs:__imp_ConvertStringSidToSidW
0x1800d7ca9  nop     dword ptr [rax+rax+00h]
0x1800d7cae  test    eax, eax
0x1800d7cb0  jz      loc_1800D7D48
0x1800d7cb6  mov     rcx, [rsp+78h+Sid]; Sid
0x1800d7cbe  call    cs:__imp_RtlLengthSid
0x1800d7cc5  nop     dword ptr [rax+rax+00h]
0x1800d7cca  mov     ecx, eax
0x1800d7ccc  mov     r12d, eax
0x1800d7ccf  call    LsapAllocate
0x1800d7cd4  mov     r15, rax
0x1800d7cd7  test    rax, rax
0x1800d7cda  jz      short loc_1800D7D00
0x1800d7cdc  mov     r8, [rsp+78h+Sid]; SourceSid
0x1800d7ce4  mov     rdx, rax; DestinationSid
0x1800d7ce7  mov     ecx, r12d; DestinationSidLength
0x1800d7cea  call    cs:__imp_RtlCopySid
0x1800d7cf1  nop     dword ptr [rax+rax+00h]
0x1800d7cf6  mov     ecx, edi
0x1800d7cf8  inc     edi
0x1800d7cfa  mov     [rbx+rcx*8], r15
0x1800d7cfe  jmp     short loc_1800D7D31
0x1800d7d00  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7d07  lea     rax, WPP_GLOBAL_Control
0x1800d7d0e  cmp     rcx, rax
0x1800d7d11  jz      short loc_1800D7D31
0x1800d7d13  test    byte ptr [rcx+1Ch], 1
0x1800d7d17  jz      short loc_1800D7D31
0x1800d7d19  mov     rcx, [rcx+10h]
0x1800d7d1d  lea     r8, WPP_0e54213bb8d436d71283068defefc09d_Traceguids
0x1800d7d24  mov     edx, 11h
0x1800d7d29  mov     r9d, r12d
0x1800d7d2c  call    WPP_SF_d
0x1800d7d31  mov     rcx, [rsp+78h+Sid]; hMem
0x1800d7d39  call    cs:__imp_LocalFree
0x1800d7d40  nop     dword ptr [rax+rax+00h]
0x1800d7d45  xor     r12d, r12d
0x1800d7d48  mov     rdx, r13
0x1800d7d4b  mov     rcx, rbp; Source
0x1800d7d4e  sub     rdx, rbp
0x1800d7d51  add     rdx, r14
0x1800d7d54  shr     rdx, 1; MaxCount
0x1800d7d57  call    cs:__imp_wcsnlen
0x1800d7d5e  nop     dword ptr [rax+rax+00h]
0x1800d7d63  lea     rbp, [rbp+rax*2+0]
0x1800d7d68  add     rbp, 2
0x1800d7d6c  lea     rax, [r14+r13]
0x1800d7d70  cmp     rbp, rax
0x1800d7d73  jb      loc_1800D7C7C
0x1800d7d79  mov     r13, [rsp+78h+arg_18]
0x1800d7d81  test    edi, edi
0x1800d7d83  jnz     short loc_1800D7D90
0x1800d7d85  mov     rcx, rbx; struct _RTL_BALANCED_NODE *
0x1800d7d88  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800d7d8d  mov     rbx, r12
0x1800d7d90  mov     rax, [rsp+78h+arg_10]
0x1800d7d98  mov     [r13+0], edi
0x1800d7d9c  mov     [rax], rbx
0x1800d7d9f  mov     rbx, [rsp+78h+arg_8]
0x1800d7da7  add     rsp, 40h
0x1800d7dab  pop     r15
0x1800d7dad  pop     r14
0x1800d7daf  pop     r13
0x1800d7db1  pop     r12
0x1800d7db3  pop     rdi
0x1800d7db4  pop     rsi
0x1800d7db5  pop     rbp
0x1800d7db6  retn
```
