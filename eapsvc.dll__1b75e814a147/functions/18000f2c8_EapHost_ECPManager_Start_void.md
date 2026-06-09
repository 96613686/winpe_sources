# EapHost::ECPManager::Start(void)

- ea: `0x18000f2c8`
- end: `0x18000f576`
- name: `?Start@ECPManager@EapHost@@QEAAXXZ`
- size: `686`
- prototype: `void __fastcall(EapHost::ECPManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ac00`

## callees

- `0x180001f60`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c39c`
- `0x18000c40c`
- `0x18000eadc`
- `0x18000f2c8`
- `0x180013578`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f4ed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f543`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f568`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f4ed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f543`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f568`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000f3e5`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000f3e5`
- `ntdll!EtwEventEnabled` at `0x18000f307`
- `ntdll!EtwEventEnabled` at `0x18000f405`
- `ntdll!EtwEventEnabled` at `0x18000f4e3`
- `ntdll!EtwEventEnabled` at `0x18000f307`
- `ntdll!EtwEventEnabled` at `0x18000f405`
- `ntdll!EtwEventEnabled` at `0x18000f4e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4ab`

## string_xrefs

- `0x18000f315`: `Preparing to start ECP thread`
- `0x18000f4f3`: `Failed to create ECP thread. errno=%u`
- `0x18000f40f`: `ECP thread successfully created.`

## pseudocode

```c
void __fastcall EapHost::ECPManager::Start(EapHost::ECPManager *this)
{
  __int64 v2; // rbx
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rax
  __int64 v6; // rsi
  int v7; // r8d
  int v8; // r9d
  char *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  _DWORD *v13; // rax
  unsigned int *v14; // rax
  unsigned int *v15; // rax
  __int64 v16; // rcx
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[16]; // [rsp+38h] [rbp-C8h] BYREF
  char *v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+54h] [rbp-ACh]
  char v22[2048]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v22, 0x800u, "Preparing to start ECP thread") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v22[v5] );
    v21 = 0;
    v20 = v5 + 1;
    v19 = v22;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v3,
      v4,
      (__int64)v18);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  EapHost::ECPDeviceManager::Initialize((LPVOID *)this + 9, *((void **)this + 2), *((_DWORD *)this + 16));
  v17 = 0;
  v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, unsigned int (__fastcall *)(EapHost::ECPManager *), EapHost::ECPManager *, _DWORD, int *))_o__beginthreadex)(
         0,
         0,
         EapHost::ECPManager::ThreadFunc,
         this,
         0,
         &v17);
  if ( !v6 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent) )
    {
      v13 = (_DWORD *)_o__errno(v11, v10, v12);
      if ( (int)StringCchPrintfA(v22, 0x800u, "Failed to create ECP thread. errno=%u", *v13) >= 0
        && (byte_180020AC1 & 8) != 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v22);
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = (unsigned int *)_o__errno(v11, v10, v12);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids, *v14);
    }
    v15 = (unsigned int *)_o__errno(v11, v10, v12);
    SystemError::Throw<int>(v16, *v15);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v22, 0x800u, "ECP thread successfully created.") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    do
      ++v2;
    while ( v22[v2] );
    v21 = 0;
    v20 = v2 + 1;
    v19 = v22;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v7,
      v8,
      (__int64)v18);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  v9 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  *((_QWORD *)this + 5) = v6;
}

```

## disassembly

```asm
0x18000f2c8  mov     [rsp-8+arg_8], rbx
0x18000f2cd  mov     [rsp-8+arg_10], rsi
0x18000f2d2  push    rbp
0x18000f2d3  push    rdi
0x18000f2d4  push    r15
0x18000f2d6  lea     rbp, [rsp-770h]
0x18000f2de  sub     rsp, 870h
0x18000f2e5  mov     rax, cs:__security_cookie
0x18000f2ec  xor     rax, rsp
0x18000f2ef  mov     [rbp+780h+var_20], rax
0x18000f2f6  mov     rdi, rcx
0x18000f2f9  lea     rdx, DebugInfoEvent
0x18000f300  mov     rcx, cs:eaphost_Context
0x18000f307  call    cs:__imp_EtwEventEnabled
0x18000f30d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f311  test    al, al
0x18000f313  jz      short loc_18000F37E
0x18000f315  lea     r8, aPreparingToSta; "Preparing to start ECP thread"
0x18000f31c  mov     edx, 800h; unsigned __int64
0x18000f321  lea     rcx, [rsp+880h+var_820]; char *
0x18000f326  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f32b  test    eax, eax
0x18000f32d  js      short loc_18000F37E
0x18000f32f  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x18000f336  jz      short loc_18000F37E
0x18000f338  lea     rcx, [rsp+880h+var_820]
0x18000f33d  mov     rax, rbx
0x18000f340  inc     rax
0x18000f343  cmp     byte ptr [rcx+rax], 0
0x18000f347  jnz     short loc_18000F340
0x18000f349  inc     eax
0x18000f34b  mov     [rsp+880h+var_82C], 0
0x18000f353  lea     rcx, [rsp+880h+var_820]
0x18000f358  mov     [rsp+880h+var_830], eax
0x18000f35c  lea     rax, [rsp+880h+var_848]
0x18000f361  mov     [rsp+880h+var_838], rcx
0x18000f366  lea     rdx, DebugInfoEvent
0x18000f36d  mov     [rsp+880h+var_860], rax
0x18000f372  lea     rcx, eaphost_Context
0x18000f379  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f37e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f385  lea     r15, WPP_GLOBAL_Control
0x18000f38c  cmp     rcx, r15
0x18000f38f  jz      short loc_18000F3AC
0x18000f391  test    byte ptr [rcx+1Ch], 4
0x18000f395  jz      short loc_18000F3AC
0x18000f397  mov     rcx, [rcx+10h]
0x18000f39b  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f3a2  mov     edx, 0Ah
0x18000f3a7  call    WPP_SF_
0x18000f3ac  mov     r8d, [rdi+40h]; unsigned int
0x18000f3b0  lea     rcx, [rdi+48h]; ppv
0x18000f3b4  mov     rdx, [rdi+10h]; void *
0x18000f3b8  call    ?Initialize@ECPDeviceManager@EapHost@@QEAAXPEAXI@Z; EapHost::ECPDeviceManager::Initialize(void *,uint)
0x18000f3bd  lea     rax, [rsp+880h+var_850]
0x18000f3c2  mov     [rsp+880h+var_850], 0
0x18000f3ca  mov     [rsp+880h+var_858], rax
0x18000f3cf  lea     r8, ?ThreadFunc@ECPManager@EapHost@@CAIPEAX@Z; EapHost::ECPManager::ThreadFunc(void *)
0x18000f3d6  mov     r9, rdi
0x18000f3d9  mov     dword ptr [rsp+880h+var_860], 0
0x18000f3e1  xor     edx, edx
0x18000f3e3  xor     ecx, ecx
0x18000f3e5  call    cs:__imp__o__beginthreadex
0x18000f3eb  mov     rcx, cs:eaphost_Context
0x18000f3f2  mov     rsi, rax
0x18000f3f5  test    rax, rax
0x18000f3f8  jz      loc_18000F4DC
0x18000f3fe  lea     rdx, DebugInfoEvent
0x18000f405  call    cs:__imp_EtwEventEnabled
0x18000f40b  test    al, al
0x18000f40d  jz      short loc_18000F476
0x18000f40f  lea     r8, aEcpThreadSucce; "ECP thread successfully created."
0x18000f416  mov     edx, 800h; unsigned __int64
0x18000f41b  lea     rcx, [rsp+880h+var_820]; char *
0x18000f420  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f425  test    eax, eax
0x18000f427  js      short loc_18000F476
0x18000f429  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x18000f430  jz      short loc_18000F476
0x18000f432  lea     rax, [rsp+880h+var_820]
0x18000f437  inc     rbx
0x18000f43a  cmp     byte ptr [rax+rbx], 0
0x18000f43e  jnz     short loc_18000F437
0x18000f440  lea     eax, [rbx+1]
0x18000f443  mov     [rsp+880h+var_82C], 0
0x18000f44b  lea     rcx, [rsp+880h+var_820]
0x18000f450  mov     [rsp+880h+var_830], eax
0x18000f454  lea     rax, [rsp+880h+var_848]
0x18000f459  mov     [rsp+880h+var_838], rcx
0x18000f45e  lea     rdx, DebugInfoEvent
0x18000f465  mov     [rsp+880h+var_860], rax
0x18000f46a  lea     rcx, eaphost_Context
0x18000f471  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f476  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f47d  cmp     rcx, r15
0x18000f480  jz      short loc_18000F49D
0x18000f482  test    byte ptr [rcx+1Ch], 4
0x18000f486  jz      short loc_18000F49D
0x18000f488  mov     rcx, [rcx+10h]
0x18000f48c  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f493  mov     edx, 0Ch
0x18000f498  call    WPP_SF_
0x18000f49d  mov     rcx, [rdi+28h]; hObject
0x18000f4a1  lea     rax, [rcx-1]
0x18000f4a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f4a9  ja      short loc_18000F4B1
0x18000f4ab  call    cs:__imp_CloseHandle
0x18000f4b1  mov     [rdi+28h], rsi
0x18000f4b5  mov     rcx, [rbp+780h+var_20]
0x18000f4bc  xor     rcx, rsp; StackCookie
0x18000f4bf  call    __security_check_cookie
0x18000f4c4  lea     r11, [rsp+880h+var_10]
0x18000f4cc  mov     rbx, [r11+28h]
0x18000f4d0  mov     rsi, [r11+30h]
0x18000f4d4  mov     rsp, r11
0x18000f4d7  pop     r15
0x18000f4d9  pop     rdi
0x18000f4da  pop     rbp
0x18000f4db  retn
0x18000f4dc  lea     rdx, DebugErrorEvent
0x18000f4e3  call    cs:__imp_EtwEventEnabled
0x18000f4e9  test    al, al
0x18000f4eb  jz      short loc_18000F531
0x18000f4ed  call    cs:__imp__o__errno
0x18000f4f3  lea     r8, aFailedToCreate_1; "Failed to create ECP thread. errno=%u"
0x18000f4fa  mov     edx, 800h; unsigned __int64
0x18000f4ff  lea     rcx, [rsp+880h+var_820]; char *
0x18000f504  mov     r9d, [rax]
0x18000f507  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f50c  test    eax, eax
0x18000f50e  js      short loc_18000F531
0x18000f510  test    cs:byte_180020AC1, 8
0x18000f517  jz      short loc_18000F531
0x18000f519  lea     r8, [rsp+880h+var_820]
0x18000f51e  lea     rdx, DebugErrorEvent
0x18000f525  lea     rcx, eaphost_Context
0x18000f52c  call    McTemplateU0s_EtwEventWriteTransfer
0x18000f531  mov     rax, cs:WPP_GLOBAL_Control
0x18000f538  cmp     rax, r15
0x18000f53b  jz      short loc_18000F568
0x18000f53d  test    byte ptr [rax+1Ch], 1
0x18000f541  jz      short loc_18000F568
0x18000f543  call    cs:__imp__o__errno
0x18000f549  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f550  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f557  mov     edx, 0Bh
0x18000f55c  mov     r9d, [rax]
0x18000f55f  mov     rcx, [rcx+10h]
0x18000f563  call    WPP_SF_d
0x18000f568  call    cs:__imp__o__errno
0x18000f56e  mov     edx, [rax]
0x18000f570  call    ??$Throw@H@SystemError@@SAXPEB_WH@Z; SystemError::Throw<int>(wchar_t const *,int)
```
