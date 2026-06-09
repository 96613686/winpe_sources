# EVENT_LOG::ReportJobCreated(ushort const *,_GUID const &,SidHandle,ulong,ushort const *,unsigned __int64)

- ea: `0x18006b4fc`
- end: `0x18006b7c5`
- name: `?ReportJobCreated@EVENT_LOG@@QEAAXPEBGAEBU_GUID@@VSidHandle@@K0_K@Z`
- size: `713`
- prototype: `void __high(const unsigned __int16 *, const struct _GUID *, struct SidHandle, unsigned int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180036504`

## callees

- `0x180016d60`
- `0x180066e20`
- `0x18006b4fc`
- `0x180099074`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800ab7b0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18006b5e0`
- `ntdll!EtwEventEnabled` at `0x18006b5e0`
- `ntdll!EtwEventWrite` at `0x18006b75d`
- `ntdll!EtwEventWrite` at `0x18006b75d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b6a2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18006b5b1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18006b695`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18006b5b1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18006b695`

## pseudocode

```c
void __fastcall EVENT_LOG::ReportJobCreated(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        void **a4,
        char a5,
        unsigned __int16 *a6,
        char a7)
{
  EVENT_LOG *v8; // r14
  void *v11; // r15
  WCHAR *v12; // rsi
  DWORD LastError; // eax
  unsigned __int64 v14; // rdx
  EVENT_LOG *v15; // rcx
  DWORD v16; // eax
  __int64 v17; // rax
  const unsigned __int16 *v18; // r8
  EVENT_LOG *v19; // rcx
  EVENT_LOG *v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  DWORD cchName; // [rsp+30h] [rbp-81h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-7Dh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-79h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-71h]
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+50h] [rbp-61h] BYREF
  __int64 v28; // [rsp+60h] [rbp-51h]
  __int64 v29; // [rsp+68h] [rbp-49h]
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+70h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+80h] [rbp-31h] BYREF
  char *v32; // [rsp+90h] [rbp-21h]
  __int64 v33; // [rsp+98h] [rbp-19h]
  char *v34; // [rsp+A0h] [rbp-11h]
  __int64 v35; // [rsp+A8h] [rbp-9h]

  v8 = g_EventLogger;
  v26 = a6;
  if ( !*(_QWORD *)g_EventLogger )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids);
LABEL_26:
    SidHandle::~SidHandle((SidHandle *)a4);
    return;
  }
  v11 = *a4;
  v12 = (WCHAR *)*((_QWORD *)g_EventLogger + 1);
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  *v12 = 0;
  LookupAccountSidLocalW(v11, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
  LastError = GetLastError();
  if ( LastError == 1332 )
  {
    EVENT_LOG::GetUnknownUserName(v12, v14);
  }
  else if ( LastError == 122 )
  {
    if ( cchReferencedDomainName + cchName <= 0xC8 )
    {
      cchName = 200 - cchReferencedDomainName;
      if ( LookupAccountSidLocalW(v11, &v12[cchReferencedDomainName], &cchName, v12, &cchReferencedDomainName, &peUse) )
      {
        v17 = -1;
        do
          ++v17;
        while ( v12[v17] );
        v12[v17] = 92;
      }
      else
      {
        v16 = GetLastError();
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, v16);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, LastError);
  }
  if ( (unsigned __int8)EtwEventEnabled(*(_QWORD *)v8, EVT_JOB_CREATION) )
  {
    EVENT_LOG::EventDataDescCreate_UnicodeString(v15, &v27, a2);
    v18 = (const unsigned __int16 *)*((_QWORD *)v8 + 1);
    v28 = a3;
    v29 = 16;
    EVENT_LOG::EventDataDescCreate_UnicodeString(v19, &v30, v18);
    EVENT_LOG::EventDataDescCreate_UnicodeString(v20, &v31, v26);
    v33 = 4;
    v32 = &a5;
    v21 = *(_QWORD *)v8;
    v34 = &a7;
    v35 = 8;
    v22 = EtwEventWrite(v21, EVT_JOB_CREATION, 6, &v27);
    if ( v22 && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, 3, v22);
    goto LABEL_26;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a4[1], 0xFFFFFFFF) == 1 )
  {
    operator delete(a4[1], 4u);
    operator delete(*a4, 0);
    a4[1] = 0;
    *a4 = 0;
  }
}

```

## disassembly

```asm
0x18006b4fc  mov     [rsp-8+arg_0], rbx
0x18006b501  push    rbp
0x18006b502  push    rsi
0x18006b503  push    rdi
0x18006b504  push    r12
0x18006b506  push    r13
0x18006b508  push    r14
0x18006b50a  push    r15
0x18006b50c  lea     rbp, [rsp-0Fh]
0x18006b511  sub     rsp, 0C0h
0x18006b518  mov     rax, cs:__security_cookie
0x18006b51f  xor     rax, rsp
0x18006b522  mov     [rbp+3Fh+var_40], rax
0x18006b526  mov     rax, [rbp+3Fh+arg_28]
0x18006b52a  mov     rbx, r9
0x18006b52d  mov     r14, cs:?g_EventLogger@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_EventLogger
0x18006b534  mov     r12, r8
0x18006b537  mov     [rbp+3Fh+var_B0], rax
0x18006b53b  mov     r13, rdx
0x18006b53e  xor     eax, eax
0x18006b540  cmp     [r14], rax
0x18006b543  jnz     short loc_18006B57E
0x18006b545  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b54c  lea     rdi, WPP_GLOBAL_Control
0x18006b553  cmp     rcx, rdi
0x18006b556  jz      loc_18006B796
0x18006b55c  test    byte ptr [rcx+1Ch], 1
0x18006b560  jz      loc_18006B796
0x18006b566  mov     rcx, [rcx+10h]
0x18006b56a  lea     edx, [rax+2Eh]
0x18006b56d  lea     r8, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids
0x18006b574  call    WPP_SF_
0x18006b579  jmp     loc_18006B796
0x18006b57e  mov     r15, [r9]
0x18006b581  lea     r8, [rsp+0F0h+cchName]; cchName
0x18006b586  mov     rsi, [r14+8]
0x18006b58a  xor     r9d, r9d; ReferencedDomainName
0x18006b58d  mov     [rsp+0F0h+cchName], eax
0x18006b591  xor     edx, edx; Name
0x18006b593  mov     [rbp+3Fh+var_BC], eax
0x18006b596  mov     rcx, r15; Sid
0x18006b599  mov     [rbp+3Fh+var_B8], eax
0x18006b59c  mov     [rsi], ax
0x18006b59f  lea     rax, [rbp+3Fh+var_B8]
0x18006b5a3  mov     [rsp+0F0h+peUse], rax; peUse
0x18006b5a8  lea     rax, [rbp+3Fh+var_BC]
0x18006b5ac  mov     [rsp+0F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18006b5b1  call    cs:__imp_LookupAccountSidLocalW
0x18006b5b7  call    cs:__imp_GetLastError
0x18006b5bd  lea     rdi, WPP_GLOBAL_Control
0x18006b5c4  cmp     eax, 534h
0x18006b5c9  jnz     short loc_18006B624
0x18006b5cb  mov     rcx, rsi; lpBuffer
0x18006b5ce  call    ?GetUnknownUserName@EVENT_LOG@@SAJPEAG_K@Z; EVENT_LOG::GetUnknownUserName(ushort *,unsigned __int64)
0x18006b5d3  xor     r15d, r15d
0x18006b5d6  mov     rcx, [r14]
0x18006b5d9  lea     rdx, EVT_JOB_CREATION
0x18006b5e0  call    cs:__imp_EtwEventEnabled
0x18006b5e6  test    al, al
0x18006b5e8  jnz     loc_18006B6F7
0x18006b5ee  mov     rax, [rbx+8]
0x18006b5f2  or      ecx, 0FFFFFFFFh
0x18006b5f5  lock xadd [rax], ecx
0x18006b5f9  cmp     ecx, 1
0x18006b5fc  jnz     loc_18006B79E
0x18006b602  lea     edx, [rcx+3]; unsigned __int64
0x18006b605  mov     rcx, [rbx+8]; void *
0x18006b609  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b60e  mov     rcx, [rbx]; void *
0x18006b611  xor     edx, edx; unsigned __int64
0x18006b613  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006b618  mov     [rbx+8], r15
0x18006b61c  mov     [rbx], r15
0x18006b61f  jmp     loc_18006B79E
0x18006b624  cmp     eax, 7Ah ; 'z'
0x18006b627  jz      short loc_18006B658
0x18006b629  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b630  cmp     rcx, rdi
0x18006b633  jz      short loc_18006B5D3
0x18006b635  test    byte ptr [rcx+1Ch], 4
0x18006b639  jz      short loc_18006B5D3
0x18006b63b  mov     rcx, [rcx+10h]
0x18006b63f  lea     r8, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids
0x18006b646  mov     edx, 11h
0x18006b64b  mov     r9d, eax
0x18006b64e  call    WPP_SF_d
0x18006b653  jmp     loc_18006B5D3
0x18006b658  mov     edx, [rbp+3Fh+var_BC]
0x18006b65b  mov     eax, 0C8h
0x18006b660  mov     ecx, [rsp+0F0h+cchName]
0x18006b664  add     ecx, edx
0x18006b666  cmp     ecx, eax
0x18006b668  ja      loc_18006B5D3
0x18006b66e  sub     eax, edx
0x18006b670  lea     r8, [rsp+0F0h+cchName]; cchName
0x18006b675  mov     [rsp+0F0h+cchName], eax
0x18006b679  lea     rdx, [rsi+rdx*2]; Name
0x18006b67d  lea     rax, [rbp+3Fh+var_B8]
0x18006b681  mov     r9, rsi; ReferencedDomainName
0x18006b684  mov     [rsp+0F0h+peUse], rax; peUse
0x18006b689  mov     rcx, r15; Sid
0x18006b68c  lea     rax, [rbp+3Fh+var_BC]
0x18006b690  mov     [rsp+0F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18006b695  call    cs:__imp_LookupAccountSidLocalW
0x18006b69b  xor     r15d, r15d
0x18006b69e  test    eax, eax
0x18006b6a0  jnz     short loc_18006B6DE
0x18006b6a2  call    cs:__imp_GetLastError
0x18006b6a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6af  cmp     rcx, rdi
0x18006b6b2  jz      loc_18006B5D6
0x18006b6b8  test    byte ptr [rcx+1Ch], 4
0x18006b6bc  jz      loc_18006B5D6
0x18006b6c2  mov     rcx, [rcx+10h]
0x18006b6c6  lea     edx, [r15+12h]
0x18006b6ca  mov     r9d, eax
0x18006b6cd  lea     r8, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids
0x18006b6d4  call    WPP_SF_d
0x18006b6d9  jmp     loc_18006B5D6
0x18006b6de  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006b6e2  inc     rax
0x18006b6e5  cmp     [rsi+rax*2], r15w
0x18006b6ea  jnz     short loc_18006B6E2
0x18006b6ec  mov     word ptr [rsi+rax*2], 5Ch ; '\'
0x18006b6f2  jmp     loc_18006B5D6
0x18006b6f7  mov     r8, r13; unsigned __int16 *
0x18006b6fa  lea     rdx, [rbp+3Fh+var_A0]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b6fe  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b703  mov     r8, [r14+8]; unsigned __int16 *
0x18006b707  lea     rdx, [rbp+3Fh+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b70b  mov     [rbp+3Fh+var_90], r12
0x18006b70f  mov     [rbp+3Fh+var_88], 10h
0x18006b717  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b71c  mov     r8, [rbp+3Fh+var_B0]; unsigned __int16 *
0x18006b720  lea     rdx, [rbp+3Fh+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x18006b724  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18006b729  lea     rcx, [rbp+3Fh+arg_20]
0x18006b72d  mov     [rbp+3Fh+var_58], 4
0x18006b735  mov     [rbp+3Fh+var_60], rcx
0x18006b739  lea     rax, [rbp+3Fh+arg_30]
0x18006b73d  mov     rcx, [r14]
0x18006b740  lea     r9, [rbp+3Fh+var_A0]
0x18006b744  mov     r8d, 6
0x18006b74a  mov     [rbp+3Fh+var_50], rax
0x18006b74e  lea     rdx, EVT_JOB_CREATION
0x18006b755  mov     [rbp+3Fh+var_48], 8
0x18006b75d  call    cs:__imp_EtwEventWrite
0x18006b763  test    eax, eax
0x18006b765  jz      short loc_18006B796
0x18006b767  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b76e  cmp     rcx, rdi
0x18006b771  jz      short loc_18006B796
0x18006b773  test    byte ptr [rcx+1Ch], 4
0x18006b777  jz      short loc_18006B796
0x18006b779  mov     rcx, [rcx+10h]
0x18006b77d  lea     r8, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids
0x18006b784  mov     edx, 2Fh ; '/'
0x18006b789  mov     dword ptr [rsp+0F0h+cchReferencedDomainName], eax
0x18006b78d  lea     r9d, [rdx-2Ch]
0x18006b791  call    WPP_SF_Dd
0x18006b796  mov     rcx, rbx; this
0x18006b799  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x18006b79e  mov     rcx, [rbp+3Fh+var_40]
0x18006b7a2  xor     rcx, rsp; StackCookie
0x18006b7a5  call    __security_check_cookie
0x18006b7aa  mov     rbx, [rsp+0F0h+arg_0]
0x18006b7b2  add     rsp, 0C0h
0x18006b7b9  pop     r15
0x18006b7bb  pop     r14
0x18006b7bd  pop     r13
0x18006b7bf  pop     r12
0x18006b7c1  pop     rdi
0x18006b7c2  pop     rsi
0x18006b7c3  pop     rbp
0x18006b7c4  retn
```
