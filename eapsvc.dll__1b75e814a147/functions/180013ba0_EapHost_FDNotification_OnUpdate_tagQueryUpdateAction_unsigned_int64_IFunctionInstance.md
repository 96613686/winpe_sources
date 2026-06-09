# EapHost::FDNotification::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)

- ea: `0x180013ba0`
- end: `0x18001424b`
- name: `?OnUpdate@FDNotification@EapHost@@UEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z`
- size: `1707`
- prototype: `__int64 __fastcall(EapHost::FDNotification *this, enum tagQueryUpdateAction, __int64, struct IFunctionInstance *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001f60`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c39c`
- `0x18000c40c`
- `0x18000d338`
- `0x18000d610`
- `0x180013ba0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014132`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014132`
- `ntdll!EtwEventEnabled` at `0x180013bef`
- `ntdll!EtwEventEnabled` at `0x180013cbf`
- `ntdll!EtwEventEnabled` at `0x180013d7d`
- `ntdll!EtwEventEnabled` at `0x180013e6a`
- `ntdll!EtwEventEnabled` at `0x180013f63`
- `ntdll!EtwEventEnabled` at `0x18001408e`
- `ntdll!EtwEventEnabled` at `0x180014153`
- `ntdll!EtwEventEnabled` at `0x180013bef`
- `ntdll!EtwEventEnabled` at `0x180013cbf`
- `ntdll!EtwEventEnabled` at `0x180013d7d`
- `ntdll!EtwEventEnabled` at `0x180013e6a`
- `ntdll!EtwEventEnabled` at `0x180013f63`
- `ntdll!EtwEventEnabled` at `0x18001408e`
- `ntdll!EtwEventEnabled` at `0x180014153`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014029`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014216`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014029`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014216`

## string_xrefs

- `0x180013e77`: `Failed to open property store in FD update notification processiong 0x%x`
- `0x180013f70`: `Failed to get PKEY_ECP_NOTIFY_ID value during FD update notification processiong 0x%x`

## pseudocode

```c
__int64 __fastcall EapHost::FDNotification::OnUpdate(
        EapHost::FDNotification *this,
        enum tagQueryUpdateAction a2,
        __int64 a3,
        struct IFunctionInstance *a4)
{
  unsigned int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rdi
  __int64 v10; // rax
  int v11; // r8d
  int v12; // r9d
  int v13; // r8d
  int v14; // r9d
  int v15; // esi
  int v16; // r8d
  int v17; // r9d
  int v18; // r8d
  int v19; // r9d
  const wchar_t *v21; // rcx
  __int64 v22; // rax
  size_t v23; // r8
  int v24; // r8d
  int v25; // r9d
  int v26; // r8d
  int v27; // r9d
  __int64 *v28; // rbp
  unsigned int v29; // ebx
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rcx
  __int64 v33; // rax
  _QWORD *v34; // rcx
  __int64 *v35; // rdx
  __int64 v36; // [rsp+0h] [rbp-8B8h] BYREF
  __int64 v37; // [rsp+30h] [rbp-888h] BYREF
  struct IFunctionInstance *v38; // [rsp+38h] [rbp-880h]
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-878h] BYREF
  __int64 v40; // [rsp+50h] [rbp-868h]
  const Exception *v41; // [rsp+58h] [rbp-860h] BYREF
  _BYTE v42[16]; // [rsp+60h] [rbp-858h] BYREF
  char *v43; // [rsp+70h] [rbp-848h]
  int v44; // [rsp+78h] [rbp-840h]
  int v45; // [rsp+7Ch] [rbp-83Ch]
  char v46[2048]; // [rsp+80h] [rbp-838h] BYREF

  v38 = a4;
  *(_OWORD *)pvar = 0;
  v40 = 0;
  v6 = 0;
  v37 = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v46,
              0x800u,
              "Got some notification action: %u.  Need to check whether it is what we are waiting for",
              a2) >= 0 )
  {
    v9 = -1;
    if ( Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v46[v10] );
      v43 = v46;
      v44 = v10 + 1;
      v45 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (_QWORD *)(unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v7,
        v8,
        (__int64)v42);
    }
  }
  else
  {
    v9 = -1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22u, (__int64)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids, a2);
  if ( !*((_BYTE *)this + 44) )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v46, 0x800u, "We are not setup for wait yet.  Ignore the notification") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v9;
      while ( v46[v9] );
      v43 = v46;
      v44 = v9 + 1;
      v45 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (_QWORD *)(unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v11,
        v12,
        (__int64)v42);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23u, (__int64)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids);
    goto LABEL_55;
  }
  if ( a2 != *((_DWORD *)this + 10) )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v46, 0x800u, "Ignore this notification because of mismatched action") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v9;
      while ( v46[v9] );
      v43 = v46;
      v44 = v9 + 1;
      v45 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (_QWORD *)(unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v13,
        v14,
        (__int64)v42);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24u, (__int64)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids);
    goto LABEL_55;
  }
  v15 = ((__int64 (__fastcall *)(struct IFunctionInstance *, _QWORD, __int64 *))v38->lpVtbl->OpenPropertyStore)(
          v38,
          0,
          &v37);
  if ( v15 < 0 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v46,
                0x800u,
                "Failed to open property store in FD update notification processiong 0x%x",
                v15) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      do
        ++v9;
      while ( v46[v9] );
      v43 = v46;
      v44 = v9 + 1;
      v45 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (_QWORD *)(unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v16,
        v17,
        (__int64)v42);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25u, (__int64)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids, v15);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
LABEL_54:
    v6 = v15;
LABEL_55:
    PropVariantClear(pvar);
    return v6;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v37 + 40LL))(
          v37,
          qword_18001B238,
          pvar);
  if ( v15 < 0 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(
                v46,
                0x800u,
                "Failed to get PKEY_ECP_NOTIFY_ID value during FD update notification processiong 0x%x",
                v15) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      do
        ++v9;
      while ( v46[v9] );
      v43 = v46;
      v44 = v9 + 1;
      v45 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (_QWORD *)(unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v18,
        v19,
        (__int64)v42);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26u, (__int64)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids, v15);
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    goto LABEL_54;
  }
  if ( LOWORD(pvar[0]) != 31 )
    goto LABEL_76;
  v21 = (const wchar_t *)((char *)this + 48);
  v22 = -1;
  do
    ++v22;
  while ( *((_WORD *)pvar[1] + v22) );
  v23 = *((_QWORD *)this + 8);
  if ( *((_QWORD *)this + 9) > 7u )
    v21 = *(const wchar_t **)v21;
  if ( v23 == v22 && (!v23 || !wmemcmp(v21, (const wchar_t *)pvar[1], v23)) )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v46, 0x800u, "Got the right notification. Set the event.") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v9;
      while ( v46[v9] );
      v43 = v46;
      v44 = v9 + 1;
      v45 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (_QWORD *)(unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v24,
        v25,
        (__int64)v42);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27u, (__int64)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids);
    if ( !SetEvent(*((HANDLE *)this + 3)) )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        SystemError::Throw(L"SetEvent");
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v41) )
        {
          v35 = &v36;
          v28 = v35;
          v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35[11] + 8LL))(v35[11]);
          *((_DWORD *)v28 + 14) = v29;
          if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
            && (int)StringCchPrintfA(
                      (char *)v28 + 128,
                      0x800u,
                      "Got exception while processing FD update notification, 0x%x",
                      v29) >= 0
            && (byte_180020AC1 & 8) != 0 )
          {
            v32 = v28 + 16;
            v33 = -1;
            do
              ++v33;
            while ( *((_BYTE *)v32 + v33) );
            v28[14] = (__int64)(v28 + 16);
            *((_DWORD *)v28 + 30) = v33 + 1;
            *((_DWORD *)v28 + 31) = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (_QWORD *)(unsigned int)&eaphost_Context,
              (unsigned int)DebugErrorEvent,
              v30,
              v31,
              (__int64)(v28 + 12));
          }
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 1) != 0 )
            WPP_SF_d(v34[2], 29u, (__int64)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids, v29);
          v15 = (int)v38;
          __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_1800141F6);
        }
      }
    }
  }
  else
  {
LABEL_76:
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v46, 0x800u, "PKEY_ECP_NOTIFY_ID does not match. Ignore the notification") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v9;
      while ( v46[v9] );
      v43 = v46;
      v44 = v9 + 1;
      v45 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (_QWORD *)(unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v26,
        v27,
        (__int64)v42);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28u, (__int64)WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids);
  }
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  PropVariantClear(pvar);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180013ba0  push    rbx
0x180013ba2  push    rsi
0x180013ba3  push    rdi
0x180013ba4  push    r13
0x180013ba6  push    r14
0x180013ba8  sub     rsp, 890h
0x180013baf  mov     rax, cs:__security_cookie
0x180013bb6  xor     rax, rsp
0x180013bb9  mov     [rsp+8B8h+var_38], rax
0x180013bc1  mov     [rsp+8B8h+var_880], r9
0x180013bc6  mov     esi, edx
0x180013bc8  mov     r13, rcx
0x180013bcb  xorps   xmm0, xmm0
0x180013bce  xor     eax, eax
0x180013bd0  movups  xmmword ptr [rsp+8B8h+pvar], xmm0
0x180013bd5  mov     [rsp+8B8h+var_868], rax
0x180013bda  xor     ebx, ebx
0x180013bdc  mov     [rsp+8B8h+var_888], rbx
0x180013be1  lea     rdx, DebugInfoEvent
0x180013be8  mov     rcx, cs:eaphost_Context
0x180013bef  call    cs:__imp_EtwEventEnabled
0x180013bf5  mov     r14d, 800h
0x180013bfb  test    al, al
0x180013bfd  jz      short loc_180013C72
0x180013bff  mov     r9d, esi
0x180013c02  lea     r8, aGotSomeNotific; "Got some notification action: %u.  Need"...
0x180013c09  mov     edx, r14d; unsigned __int64
0x180013c0c  lea     rcx, [rsp+8B8h+var_838]; char *
0x180013c14  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013c19  test    eax, eax
0x180013c1b  js      short loc_180013C72
0x180013c1d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013c21  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180013c27  jge     short loc_180013C76
0x180013c29  lea     rcx, [rsp+8B8h+var_838]
0x180013c31  mov     rax, rdi
0x180013c34  inc     rax
0x180013c37  cmp     [rcx+rax], bl
0x180013c3a  jnz     short loc_180013C34
0x180013c3c  inc     eax
0x180013c3e  lea     rcx, [rsp+8B8h+var_838]
0x180013c46  mov     [rsp+8B8h+var_848], rcx
0x180013c4b  mov     [rsp+8B8h+var_840], eax
0x180013c4f  mov     [rsp+8B8h+var_83C], ebx
0x180013c53  lea     rax, [rsp+8B8h+var_858]
0x180013c58  mov     [rsp+8B8h+var_898], rax
0x180013c5d  lea     rdx, DebugInfoEvent
0x180013c64  lea     rcx, eaphost_Context
0x180013c6b  call    McGenEventWrite_EtwEventWriteTransfer
0x180013c70  jmp     short loc_180013C76
0x180013c72  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013c76  lea     rax, WPP_GLOBAL_Control
0x180013c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c84  cmp     rcx, rax
0x180013c87  jz      short loc_180013CA7
0x180013c89  test    byte ptr [rcx+1Ch], 4
0x180013c8d  jz      short loc_180013CA7
0x180013c8f  mov     edx, 16h
0x180013c94  mov     r9d, esi
0x180013c97  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180013c9e  mov     rcx, [rcx+10h]
0x180013ca2  call    WPP_SF_d
0x180013ca7  cmp     [r13+2Ch], bl
0x180013cab  jnz     loc_180013D65
0x180013cb1  lea     rdx, DebugInfoEvent
0x180013cb8  mov     rcx, cs:eaphost_Context
0x180013cbf  call    cs:__imp_EtwEventEnabled
0x180013cc5  test    al, al
0x180013cc7  jz      short loc_180013D31
0x180013cc9  lea     r8, aWeAreNotSetupF; "We are not setup for wait yet.  Ignore "...
0x180013cd0  mov     rdx, r14; unsigned __int64
0x180013cd3  lea     rcx, [rsp+8B8h+var_838]; char *
0x180013cdb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013ce0  test    eax, eax
0x180013ce2  js      short loc_180013D31
0x180013ce4  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180013cea  jge     short loc_180013D31
0x180013cec  lea     rax, [rsp+8B8h+var_838]
0x180013cf4  inc     rdi
0x180013cf7  cmp     [rax+rdi], bl
0x180013cfa  jnz     short loc_180013CF4
0x180013cfc  lea     eax, [rdi+1]
0x180013cff  lea     rcx, [rsp+8B8h+var_838]
0x180013d07  mov     [rsp+8B8h+var_848], rcx
0x180013d0c  mov     [rsp+8B8h+var_840], eax
0x180013d10  mov     [rsp+8B8h+var_83C], ebx
0x180013d14  lea     rax, [rsp+8B8h+var_858]
0x180013d19  mov     [rsp+8B8h+var_898], rax
0x180013d1e  lea     rdx, DebugInfoEvent
0x180013d25  lea     rcx, eaphost_Context
0x180013d2c  call    McGenEventWrite_EtwEventWriteTransfer
0x180013d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d38  lea     rax, WPP_GLOBAL_Control
0x180013d3f  cmp     rcx, rax
0x180013d42  jz      short loc_180013D60
0x180013d44  test    byte ptr [rcx+1Ch], 4
0x180013d48  jz      short loc_180013D60
0x180013d4a  mov     edx, 17h
0x180013d4f  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180013d56  mov     rcx, [rcx+10h]
0x180013d5a  call    WPP_SF_
0x180013d5f  nop
0x180013d60  jmp     loc_180013E1E
0x180013d65  cmp     esi, [r13+28h]
0x180013d69  jz      loc_180013E3A
0x180013d6f  lea     rdx, DebugInfoEvent
0x180013d76  mov     rcx, cs:eaphost_Context
0x180013d7d  call    cs:__imp_EtwEventEnabled
0x180013d83  test    al, al
0x180013d85  jz      short loc_180013DEF
0x180013d87  lea     r8, aIgnoreThisNoti; "Ignore this notification because of mis"...
0x180013d8e  mov     rdx, r14; unsigned __int64
0x180013d91  lea     rcx, [rsp+8B8h+var_838]; char *
0x180013d99  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013d9e  test    eax, eax
0x180013da0  js      short loc_180013DEF
0x180013da2  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x180013da8  jge     short loc_180013DEF
0x180013daa  lea     rax, [rsp+8B8h+var_838]
0x180013db2  inc     rdi
0x180013db5  cmp     [rax+rdi], bl
0x180013db8  jnz     short loc_180013DB2
0x180013dba  lea     eax, [rdi+1]
0x180013dbd  lea     rcx, [rsp+8B8h+var_838]
0x180013dc5  mov     [rsp+8B8h+var_848], rcx
0x180013dca  mov     [rsp+8B8h+var_840], eax
0x180013dce  mov     [rsp+8B8h+var_83C], ebx
0x180013dd2  lea     rax, [rsp+8B8h+var_858]
0x180013dd7  mov     [rsp+8B8h+var_898], rax
0x180013ddc  lea     rdx, DebugInfoEvent
0x180013de3  lea     rcx, eaphost_Context
0x180013dea  call    McGenEventWrite_EtwEventWriteTransfer
0x180013def  mov     rcx, cs:WPP_GLOBAL_Control
0x180013df6  lea     rax, WPP_GLOBAL_Control
0x180013dfd  cmp     rcx, rax
0x180013e00  jz      short loc_180013E1E
0x180013e02  test    byte ptr [rcx+1Ch], 4
0x180013e06  jz      short loc_180013E1E
0x180013e08  mov     edx, 18h
0x180013e0d  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180013e14  mov     rcx, [rcx+10h]
0x180013e18  call    WPP_SF_
0x180013e1d  nop
0x180013e1e  mov     rcx, [rsp+8B8h+var_888]
0x180013e23  test    rcx, rcx
0x180013e26  jz      short loc_180013E35
0x180013e28  mov     rax, [rcx]
0x180013e2b  mov     rax, [rax+10h]
0x180013e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e34  nop
0x180013e35  jmp     loc_180014024
0x180013e3a  mov     rcx, [rsp+8B8h+var_880]
0x180013e3f  mov     rax, [rcx]
0x180013e42  lea     r8, [rsp+8B8h+var_888]
0x180013e47  xor     edx, edx
0x180013e49  mov     rax, [rax+30h]
0x180013e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e52  mov     esi, eax
0x180013e54  test    eax, eax
0x180013e56  jns     loc_180013F2E
0x180013e5c  lea     rdx, DebugErrorEvent
0x180013e63  mov     rcx, cs:eaphost_Context
0x180013e6a  call    cs:__imp_EtwEventEnabled
0x180013e70  test    al, al
0x180013e72  jz      short loc_180013EE0
0x180013e74  mov     r9d, esi
0x180013e77  lea     r8, aFailedToOpenPr; "Failed to open property store in FD upd"...
0x180013e7e  mov     rdx, r14; unsigned __int64
0x180013e81  lea     rcx, [rsp+8B8h+var_838]; char *
0x180013e89  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013e8e  test    eax, eax
0x180013e90  js      short loc_180013EE0
0x180013e92  test    cs:byte_180020AC1, 8
0x180013e99  jz      short loc_180013EE0
0x180013e9b  lea     rax, [rsp+8B8h+var_838]
0x180013ea3  inc     rdi
0x180013ea6  cmp     [rax+rdi], bl
0x180013ea9  jnz     short loc_180013EA3
0x180013eab  lea     eax, [rdi+1]
0x180013eae  lea     rcx, [rsp+8B8h+var_838]
0x180013eb6  mov     [rsp+8B8h+var_848], rcx
0x180013ebb  mov     [rsp+8B8h+var_840], eax
0x180013ebf  mov     [rsp+8B8h+var_83C], ebx
0x180013ec3  lea     rax, [rsp+8B8h+var_858]
0x180013ec8  mov     [rsp+8B8h+var_898], rax
0x180013ecd  lea     rdx, DebugErrorEvent
0x180013ed4  lea     rcx, eaphost_Context
0x180013edb  call    McGenEventWrite_EtwEventWriteTransfer
0x180013ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ee7  lea     rax, WPP_GLOBAL_Control
0x180013eee  cmp     rcx, rax
0x180013ef1  jz      short loc_180013F12
0x180013ef3  test    byte ptr [rcx+1Ch], 1
0x180013ef7  jz      short loc_180013F12
0x180013ef9  mov     edx, 19h
0x180013efe  mov     r9d, esi
0x180013f01  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180013f08  mov     rcx, [rcx+10h]
0x180013f0c  call    WPP_SF_d
0x180013f11  nop
0x180013f12  mov     rcx, [rsp+8B8h+var_888]
0x180013f17  test    rcx, rcx
0x180013f1a  jz      short loc_180013F29
0x180013f1c  mov     rax, [rcx]
0x180013f1f  mov     rax, [rax+10h]
0x180013f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f28  nop
0x180013f29  jmp     loc_180014022
0x180013f2e  mov     rcx, [rsp+8B8h+var_888]
0x180013f33  mov     rax, [rcx]
0x180013f36  lea     r8, [rsp+8B8h+pvar]
0x180013f3b  lea     rdx, qword_18001B238
0x180013f42  mov     rax, [rax+28h]
0x180013f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f4b  mov     esi, eax
0x180013f4d  test    eax, eax
0x180013f4f  jns     loc_180014036
0x180013f55  lea     rdx, DebugErrorEvent
0x180013f5c  mov     rcx, cs:eaphost_Context
0x180013f63  call    cs:__imp_EtwEventEnabled
0x180013f69  test    al, al
0x180013f6b  jz      short loc_180013FD9
0x180013f6d  mov     r9d, esi
0x180013f70  lea     r8, aFailedToGetPke; "Failed to get PKEY_ECP_NOTIFY_ID value "...
0x180013f77  mov     rdx, r14; unsigned __int64
0x180013f7a  lea     rcx, [rsp+8B8h+var_838]; char *
0x180013f82  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013f87  test    eax, eax
0x180013f89  js      short loc_180013FD9
0x180013f8b  test    cs:byte_180020AC1, 8
0x180013f92  jz      short loc_180013FD9
0x180013f94  lea     rax, [rsp+8B8h+var_838]
0x180013f9c  inc     rdi
0x180013f9f  cmp     [rax+rdi], bl
0x180013fa2  jnz     short loc_180013F9C
0x180013fa4  lea     eax, [rdi+1]
0x180013fa7  lea     rcx, [rsp+8B8h+var_838]
0x180013faf  mov     [rsp+8B8h+var_848], rcx
0x180013fb4  mov     [rsp+8B8h+var_840], eax
0x180013fb8  mov     [rsp+8B8h+var_83C], ebx
0x180013fbc  lea     rax, [rsp+8B8h+var_858]
0x180013fc1  mov     [rsp+8B8h+var_898], rax
0x180013fc6  lea     rdx, DebugErrorEvent
0x180013fcd  lea     rcx, eaphost_Context
0x180013fd4  call    McGenEventWrite_EtwEventWriteTransfer
0x180013fd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fe0  lea     rax, WPP_GLOBAL_Control
0x180013fe7  cmp     rcx, rax
0x180013fea  jz      short loc_18001400B
0x180013fec  test    byte ptr [rcx+1Ch], 1
0x180013ff0  jz      short loc_18001400B
0x180013ff2  mov     edx, 1Ah
0x180013ff7  mov     r9d, esi
0x180013ffa  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180014001  mov     rcx, [rcx+10h]
0x180014005  call    WPP_SF_d
0x18001400a  nop
0x18001400b  mov     rcx, [rsp+8B8h+var_888]
0x180014010  test    rcx, rcx
0x180014013  jz      short loc_180014022
0x180014015  mov     rax, [rcx]
0x180014018  mov     rax, [rax+10h]
0x18001401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014021  nop
0x180014022  mov     ebx, esi
0x180014024  lea     rcx, [rsp+8B8h+pvar]; pvar
0x180014029  call    cs:__imp_PropVariantClear
0x18001402f  mov     eax, ebx
0x180014031  jmp     loc_18001421E
0x180014036  cmp     word ptr [rsp+8B8h+pvar], 1Fh
0x18001403c  jnz     loc_180014145
0x180014042  mov     rdx, [rsp+8B8h+pvar+8]; S2
0x180014047  lea     rcx, [r13+30h]
0x18001404b  mov     rax, rdi
0x18001404e  inc     rax
0x180014051  cmp     [rdx+rax*2], bx
0x180014055  jnz     short loc_18001404E
0x180014057  mov     r8, [rcx+10h]; N
0x18001405b  cmp     qword ptr [rcx+18h], 7
0x180014060  jbe     short loc_180014065
0x180014062  mov     rcx, [rcx]; S1
0x180014065  cmp     r8, rax
0x180014068  jnz     loc_180014145
0x18001406e  test    r8, r8
0x180014071  jz      short loc_180014080
0x180014073  call    wmemcmp
0x180014078  test    eax, eax
0x18001407a  jnz     loc_180014145
0x180014080  lea     rdx, DebugInfoEvent
0x180014087  mov     rcx, cs:eaphost_Context
0x18001408e  call    cs:__imp_EtwEventEnabled
0x180014094  test    al, al
0x180014096  jz      short loc_180014100
0x180014098  lea     r8, aGotTheRightNot; "Got the right notification. Set the eve"...
0x18001409f  mov     rdx, r14; unsigned __int64
0x1800140a2  lea     rcx, [rsp+8B8h+var_838]; char *
0x1800140aa  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800140af  test    eax, eax
0x1800140b1  js      short loc_180014100
0x1800140b3  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
  ... truncated ...
```
