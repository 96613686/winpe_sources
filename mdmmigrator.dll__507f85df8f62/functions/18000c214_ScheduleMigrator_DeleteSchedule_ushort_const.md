# ScheduleMigrator::DeleteSchedule(ushort const *)

- ea: `0x18000c214`
- end: `0x18000c3f2`
- name: `?DeleteSchedule@ScheduleMigrator@@QEAAJPEBG@Z`
- size: `478`
- prototype: `__int64 __fastcall(ScheduleMigrator *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180007890`
- `0x180008940`
- `0x18000c740`

## callees

- `0x18000174c`
- `0x1800022e0`
- `0x1800033dc`
- `0x180007b38`
- `0x18000c214`
- `0x180016ca8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c3b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c3c7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c3b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c3c7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c23e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c23e`

## string_xrefs

- `0x18000c269`: `MDMAppInstallationTask`
- `0x18000c295`: `MDMMaintenenceTask`
- `0x18000c2b2`: `Could not delete task`
- `0x18000c340`: `MDMMaintenenceTaskUser`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::DeleteSchedule(ScheduleMigrator *this, const unsigned __int16 *a2)
{
  HRESULT v3; // esi
  BOOL v4; // ebx
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rcx
  const unsigned __int16 *v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *v9; // rax
  unsigned __int16 *i; // rdi
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v14; // r9
  const char *v16; // [rsp+30h] [rbp-A8h] BYREF
  BOOL v17; // [rsp+38h] [rbp-A0h]
  const unsigned __int16 *v18[2]; // [rsp+40h] [rbp-98h] BYREF
  unsigned __int16 v19[8]; // [rsp+50h] [rbp-88h] BYREF
  __int128 v20; // [rsp+60h] [rbp-78h]
  _OWORD v21[2]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v22; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v3 = CoInitializeEx(0, 0);
  v4 = v3 >= 0;
  v17 = v4;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  try
  {
    std::wstring::_Construct<1,unsigned short const *>(v19, L"MDMAppInstallationTask", 0x16u);
    memset(v21, 0, sizeof(v21));
    std::wstring::_Construct<1,unsigned short const *>(v21, L"MDMMaintenenceTask", 0x12u);
    for ( i = v19; i != (unsigned __int16 *)&v22; i += 16 )
    {
      if ( *((_QWORD *)i + 3) <= 7u )
        v5 = i;
      else
        v5 = *(const unsigned __int16 **)i;
      v3 = DeleteTask(v5, 0, v7);
      if ( ((v3 + 0x80000000) & 0x80000000) == 0 && v3 != -2147024894 && (unsigned int)dword_18002B0C0 > 5 )
      {
        if ( *((_QWORD *)i + 3) <= 7u )
          v9 = i;
        else
          v9 = *(const unsigned __int16 **)i;
        v16 = (const char *)v9;
        v18[0] = (const unsigned __int16 *)"Could not delete task";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)&dword_1800256C4,
          (__int64)v7,
          v8,
          v18,
          (const unsigned __int16 **)&v16);
      }
    }
    if ( a2 )
    {
      v3 = DeleteTask(L"MDMMaintenenceTaskUser", a2, v7);
      if ( ((v3 + 0x80000000) & 0x80000000) == 0 && v3 != -2147024894 && (unsigned int)dword_18002B0C0 > 5 )
      {
        v18[0] = L"MDMMaintenenceTaskUser";
        v16 = "Could not delete task";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v11,
          (__int64)&dword_180025684,
          v12,
          v13,
          (const unsigned __int16 **)&v16,
          v18);
      }
    }
    `eh vector destructor iterator'(v19, 0x20u, 2u, (void (*)(void *))std::wstring::~wstring);
  }
  catch ( ... )
  {
    LODWORD(v16) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x8E,
                     (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\schedulemigrator.cpp",
                     v14);
    if ( v17 )
      CoUninitialize();
    return (unsigned int)v16;
  }
  if ( v4 )
    CoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000c214  push    rbx
0x18000c216  push    rsi
0x18000c217  push    rdi
0x18000c218  push    r13
0x18000c21a  push    r14
0x18000c21c  push    r15
0x18000c21e  sub     rsp, 0A8h
0x18000c225  mov     rax, cs:__security_cookie
0x18000c22c  xor     rax, rsp
0x18000c22f  mov     [rsp+0D8h+var_48], rax
0x18000c237  mov     r14, rdx
0x18000c23a  xor     edx, edx; dwCoInit
0x18000c23c  xor     ecx, ecx; pvReserved
0x18000c23e  call    cs:__imp_CoInitializeEx
0x18000c244  mov     esi, eax
0x18000c246  xor     ebx, ebx
0x18000c248  lea     eax, [rbx+1]
0x18000c24b  test    esi, esi
0x18000c24d  cmovns  ebx, eax
0x18000c250  mov     [rsp+0D8h+var_A0], ebx
0x18000c254  xorps   xmm0, xmm0
0x18000c257  movups  xmmword ptr [rsp+0D8h+var_88], xmm0
0x18000c25c  xorps   xmm1, xmm1
0x18000c25f  movdqa  [rsp+0D8h+var_78], xmm1
0x18000c265  lea     r8d, [rax+15h]
0x18000c269  lea     rdx, aMdmappinstalla; "MDMAppInstallationTask"
0x18000c270  lea     rcx, [rsp+0D8h+var_88]
0x18000c275  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000c27a  nop
0x18000c27b  xorps   xmm0, xmm0
0x18000c27e  movups  [rsp+0D8h+var_68], xmm0
0x18000c283  xorps   xmm1, xmm1
0x18000c286  movdqa  [rsp+0D8h+var_58], xmm1
0x18000c28f  mov     r8d, 12h
0x18000c295  lea     rdx, aMdmmaintenence_0; "MDMMaintenenceTask"
0x18000c29c  lea     rcx, [rsp+0D8h+var_68]
0x18000c2a1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000c2a6  nop
0x18000c2a7  lea     rdi, [rsp+0D8h+var_88]
0x18000c2ac  mov     r15d, 80000000h
0x18000c2b2  lea     r13, aCouldNotDelete; "Could not delete task"
0x18000c2b9  lea     rax, [rsp+0D8h+var_48]
0x18000c2c1  cmp     rdi, rax
0x18000c2c4  jz      short loc_18000C338
0x18000c2c6  cmp     qword ptr [rdi+18h], 7
0x18000c2cb  jbe     short loc_18000C2D2
0x18000c2cd  mov     rcx, [rdi]
0x18000c2d0  jmp     short loc_18000C2D5
0x18000c2d2  mov     rcx, rdi; unsigned __int16 *
0x18000c2d5  xor     edx, edx; unsigned __int16 *
0x18000c2d7  call    ?DeleteTask@@YAJPEBG00@Z; DeleteTask(ushort const *,ushort const *,ushort const *)
0x18000c2dc  mov     esi, eax
0x18000c2de  add     eax, r15d
0x18000c2e1  test    r15d, eax
0x18000c2e4  jnz     short loc_18000C332
0x18000c2e6  cmp     esi, 80070002h
0x18000c2ec  jz      short loc_18000C332
0x18000c2ee  mov     eax, cs:dword_18002B0C0
0x18000c2f4  cmp     eax, 5
0x18000c2f7  jbe     short loc_18000C332
0x18000c2f9  cmp     qword ptr [rdi+18h], 7
0x18000c2fe  jbe     short loc_18000C305
0x18000c300  mov     rax, [rdi]
0x18000c303  jmp     short loc_18000C308
0x18000c305  mov     rax, rdi
0x18000c308  mov     [rsp+0D8h+var_A8], rax
0x18000c30d  mov     [rsp+0D8h+var_98], r13
0x18000c312  lea     rax, [rsp+0D8h+var_A8]
0x18000c317  mov     [rsp+0D8h+var_B0], rax
0x18000c31c  lea     rax, [rsp+0D8h+var_98]
0x18000c321  mov     [rsp+0D8h+var_B8], rax
0x18000c326  lea     rdx, dword_1800256C4
0x18000c32d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000c332  add     rdi, 20h ; ' '
0x18000c336  jmp     short loc_18000C2B9
0x18000c338  test    r14, r14
0x18000c33b  jz      short loc_18000C397
0x18000c33d  mov     rdx, r14; unsigned __int16 *
0x18000c340  lea     rdi, aMdmmaintenence; "MDMMaintenenceTaskUser"
0x18000c347  mov     rcx, rdi; unsigned __int16 *
0x18000c34a  call    ?DeleteTask@@YAJPEBG00@Z; DeleteTask(ushort const *,ushort const *,ushort const *)
0x18000c34f  mov     esi, eax
0x18000c351  add     eax, r15d
0x18000c354  test    r15d, eax
0x18000c357  jnz     short loc_18000C397
0x18000c359  cmp     esi, 80070002h
0x18000c35f  jz      short loc_18000C397
0x18000c361  mov     eax, cs:dword_18002B0C0
0x18000c367  cmp     eax, 5
0x18000c36a  jbe     short loc_18000C397
0x18000c36c  mov     [rsp+0D8h+var_98], rdi
0x18000c371  mov     [rsp+0D8h+var_A8], r13
0x18000c376  lea     rax, [rsp+0D8h+var_98]
0x18000c37b  mov     [rsp+0D8h+var_B0], rax
0x18000c380  lea     rax, [rsp+0D8h+var_A8]
0x18000c385  mov     [rsp+0D8h+var_B8], rax
0x18000c38a  lea     rdx, dword_180025684
0x18000c391  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000c396  nop
0x18000c397  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18000c39e  mov     edx, 20h ; ' '; unsigned __int64
0x18000c3a3  lea     r8d, [rdx-1Eh]; unsigned __int64
0x18000c3a7  lea     rcx, [rsp+0D8h+var_88]; void *
0x18000c3ac  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000c3b1  nop
0x18000c3b2  test    ebx, ebx
0x18000c3b4  jz      short loc_18000C3BC
0x18000c3b6  call    cs:__imp_CoUninitialize
0x18000c3bc  mov     eax, esi
0x18000c3be  jmp     short loc_18000C3D1
0x18000c3c0  cmp     [rsp+0D8h+var_A0], 0
0x18000c3c5  jz      short loc_18000C3CD
0x18000c3c7  call    cs:__imp_CoUninitialize
0x18000c3cd  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18000c3d1  mov     rcx, [rsp+0D8h+var_48]
0x18000c3d9  xor     rcx, rsp; StackCookie
0x18000c3dc  call    __security_check_cookie
0x18000c3e1  add     rsp, 0A8h
0x18000c3e8  pop     r15
0x18000c3ea  pop     r14
0x18000c3ec  pop     r13
0x18000c3ee  pop     rdi
0x18000c3ef  pop     rsi
0x18000c3f0  pop     rbx
0x18000c3f1  retn
```
