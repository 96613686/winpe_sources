# InitializeHardwareSystem

- ea: `0x14000b1c0`
- end: `0x14000b5b8`
- name: `InitializeHardwareSystem`
- size: `1016`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000afb0`

## callees

- `0x140002c48`
- `0x140002e78`
- `0x140003dc0`
- `0x140003e00`
- `0x14000a81c`
- `0x14000a9fc`
- `0x14000acd0`
- `0x14000b1c0`
- `0x14000b5c0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000b42f`
- `ntoskrnl!KeInitializeEvent` at `0x14000b42f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000b4bd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000b4bd`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000b4ee`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000b4ee`
- `ntoskrnl!PsCreateSystemThread` at `0x14000b483`
- `ntoskrnl!PsCreateSystemThread` at `0x14000b483`
- `CEA!EACreateAggregateEvent` at `0x14000b56f`
- `CEA!EACreateAggregateEvent` at `0x14000b56f`

## string_xrefs

- `0x14000b380`: `CngChatConfiguration`
- `0x14000b3b9`: `Registry`

## pseudocode

```c
__int64 InitializeHardwareSystem()
{
  NTSTATUS v0; // ebx
  __int64 v1; // rcx
  unsigned __int64 v2; // rax
  __int64 HardwareAlgHandle; // rax
  __int64 v4; // rdx
  unsigned int v5; // edi
  unsigned int v6; // ecx
  unsigned int v7; // esi
  __int64 v8; // r14
  PVOID v9; // rcx
  char v10; // cl
  __int64 i; // rdi
  PVOID Object; // [rsp+40h] [rbp-C0h] BYREF
  void *ThreadHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+80h] [rbp-80h] BYREF
  int v17; // [rsp+88h] [rbp-78h]
  int v18; // [rsp+8Ch] [rbp-74h]
  __int64 v19; // [rsp+90h] [rbp-70h]
  __int64 v20; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v21)(); // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v22)(); // [rsp+A8h] [rbp-58h]
  __int64 *v23; // [rsp+B0h] [rbp-50h]
  _BYTE v24[688]; // [rsp+C0h] [rbp-40h] BYREF

  ThreadHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v0 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64))(g_pHwCipherFunctionTable + 8))(
         &qword_140007168,
         L"AES",
         1);
  if ( v0 >= 0 )
  {
    UpdateKeyObjectSize(qword_140007168);
    v0 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64))(g_pHwCipherFunctionTable + 8))(
           &qword_140007170,
           L"AES",
           1);
    if ( v0 >= 0 )
    {
      v0 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, const wchar_t *, __int64, _DWORD))(g_pHwCipherFunctionTable
                                                                                               + 24))(
             qword_140007170,
             L"ChainingMode",
             L"ChainingModeECB",
             32,
             0);
      if ( v0 >= 0 )
      {
        UpdateKeyObjectSize(qword_140007170);
        v1 = 0;
        v2 = 0;
        do
        {
          ++v1;
          g_config[v2 / 4] = 0;
          *(_DWORD *)&algn_1400077E4[v2] = 0x8000;
          LODWORD(qword_1400077E8[v2 / 8]) = 0x4000;
          HIDWORD(qword_1400077E8[v2 / 8]) = 0x10000;
          *(_DWORD *)&byte_1400077F0[v2] = -1;
          *(_QWORD *)&dword_1400077F4[v2 / 4] = 0;
          HIDWORD(qword_1400077F8[v2 / 8]) = 1;
          qword_1400077F8[v2 / 8 + 1] = 4096;
          LODWORD(qword_1400077F8[v2 / 8 + 2]) = 512;
          HIDWORD(qword_1400077F8[v2 / 8 + 2]) = 0x400000;
          qword_1400077F8[v2 / 8 + 4] = 0;
          v2 += 64LL;
        }
        while ( v1 != 3 );
        LogConfig("Default");
        LODWORD(Object) = 0;
        HardwareAlgHandle = GetHardwareAlgHandle(1);
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, _BYTE *, __int64, PVOID *, _DWORD))(g_pHwCipherFunctionTable
                                                                                                + 16))(
               HardwareAlgHandle,
               L"CngChatConfiguration",
               v24,
               688,
               &Object,
               0) >= 0
          && (unsigned int)Object <= 0x2B0 )
        {
          ConfigSetChatConfig(v24);
        }
        LogConfig("Provider");
        ConfigReadRegistry();
        LogConfig("Registry");
        ConfigApplyBounds();
        v4 = 0;
        g_mHwThreadsIdle = 0;
        v5 = 0;
        do
        {
          v6 = g_config[16 * v4];
          if ( v5 > v6 )
            v6 = v5;
          ++v4;
          v5 = v6;
        }
        while ( v4 != 3 );
        LogConfig("Final");
        v7 = 0;
        if ( v5 )
        {
          while ( 1 )
          {
            v8 = 7LL * v7;
            g_hwEngineState[v8] = 0;
            KeInitializeEvent((PRKEVENT)&qword_140007680[v8], NotificationEvent, 0);
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 512;
            ObjectAttributes.ObjectName = 0;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v0 = PsCreateSystemThread(
                   &ThreadHandle,
                   0,
                   &ObjectAttributes,
                   0,
                   0,
                   HardwareThreadStartFunction,
                   &g_hwEngineState[v8]);
            if ( v0 < 0 )
              break;
            Object = 0;
            ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
            v9 = Object;
            if ( !Object )
              return (unsigned int)-1073741595;
            g_hwEngineState[v8 + 2] = (__int64)Object;
            LODWORD(g_hwEngineState[v8 + 3]) = 18;
            KeSetActualBasePriorityThread(v9, 18);
            ++g_actualHardwareThreads;
            v10 = v7++;
            g_mHwThreadsIdle |= 1 << v10;
            LODWORD(g_hwEngineState[v8 + 1]) = 1 << v10;
            if ( v7 >= v5 )
              goto LABEL_17;
          }
        }
        else
        {
LABEL_17:
          for ( i = 0; i != 2; ++i )
          {
            v16 = 0;
            v17 = 0;
            v23 = &CngChatPowerConfig[4 * i];
            v20 = 0;
            v18 = 1;
            v19 = v23[1];
            v21 = EventStartCallback;
            v22 = EventStopCallback;
            EACreateAggregateEvent(&v16, v23 + 2);
          }
          g_fHwProvAvailable = 1;
        }
      }
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000b1c0  push    rbp
0x14000b1c2  push    rbx
0x14000b1c3  push    rsi
0x14000b1c4  push    rdi
0x14000b1c5  push    r12
0x14000b1c7  push    r13
0x14000b1c9  push    r14
0x14000b1cb  push    r15
0x14000b1cd  lea     rbp, [rsp-288h]
0x14000b1d5  sub     rsp, 388h
0x14000b1dc  mov     rax, cs:__security_cookie
0x14000b1e3  xor     rax, rsp
0x14000b1e6  mov     [rbp+2C0h+var_50], rax
0x14000b1ed  xorps   xmm0, xmm0
0x14000b1f0  lea     rdx, aAes; "AES"
0x14000b1f7  xor     eax, eax
0x14000b1f9  lea     rcx, qword_140007168
0x14000b200  mov     rax, cs:g_pHwCipherFunctionTable
0x14000b207  xor     r15d, r15d
0x14000b20a  movups  xmmword ptr [rsp+3C0h+ObjectAttributes.ObjectName], xmm0
0x14000b20f  mov     [rsp+3C0h+ThreadHandle], r15
0x14000b214  movups  xmmword ptr [rsp+3C0h+ObjectAttributes.Length], xmm0
0x14000b219  mov     rax, [rax+8]
0x14000b21d  lea     r12d, [r15+1]
0x14000b221  mov     r8d, r12d
0x14000b224  movups  xmmword ptr [rsp+3C0h+ObjectAttributes+1Ch], xmm0
0x14000b229  call    _guard_dispatch_icall
0x14000b22e  mov     ebx, eax
0x14000b230  test    eax, eax
0x14000b232  js      loc_14000B58B
0x14000b238  mov     rcx, cs:qword_140007168
0x14000b23f  call    UpdateKeyObjectSize
0x14000b244  mov     rax, cs:g_pHwCipherFunctionTable
0x14000b24b  lea     rdx, aAes; "AES"
0x14000b252  mov     r8d, r12d
0x14000b255  lea     rcx, qword_140007170
0x14000b25c  mov     rax, [rax+8]
0x14000b260  call    _guard_dispatch_icall
0x14000b265  mov     ebx, eax
0x14000b267  test    eax, eax
0x14000b269  js      loc_14000B58B
0x14000b26f  mov     rax, cs:g_pHwCipherFunctionTable
0x14000b276  lea     r9d, [r15+20h]
0x14000b27a  mov     rcx, cs:qword_140007170
0x14000b281  lea     r8, aChainingmodeec; "ChainingModeECB"
0x14000b288  lea     rdx, aChainingmode; "ChainingMode"
0x14000b28f  mov     dword ptr [rsp+3C0h+ClientId], r15d
0x14000b294  mov     rax, [rax+18h]
0x14000b298  call    _guard_dispatch_icall
0x14000b29d  mov     ebx, eax
0x14000b29f  test    eax, eax
0x14000b2a1  js      loc_14000B58B
0x14000b2a7  mov     rcx, cs:qword_140007170
0x14000b2ae  call    UpdateKeyObjectSize
0x14000b2b3  mov     ecx, r15d
0x14000b2b6  lea     r13, cs:140000000h
0x14000b2bd  mov     eax, r15d
0x14000b2c0  add     rcx, r12
0x14000b2c3  mov     [rax+r13+77E0h], r15d
0x14000b2cb  mov     dword ptr [rax+r13+77E4h], 8000h
0x14000b2d7  mov     dword ptr [rax+r13+77E8h], 4000h
0x14000b2e3  mov     dword ptr [rax+r13+77ECh], 10000h
0x14000b2ef  mov     dword ptr [rax+r13+77F0h], 0FFFFFFFFh
0x14000b2fb  mov     [rax+r13+77F4h], r15
0x14000b303  mov     [rax+r13+77FCh], r12d
0x14000b30b  mov     qword ptr [rax+r13+7800h], 1000h
0x14000b317  mov     dword ptr [rax+r13+7808h], 200h
0x14000b323  mov     dword ptr [rax+r13+780Ch], 400000h
0x14000b32f  mov     [rax+r13+7818h], r15
0x14000b337  lea     rax, [rax+40h]
0x14000b33b  cmp     rcx, 3
0x14000b33f  jnz     loc_14000B2C0
0x14000b345  lea     rcx, aDefault; "Default"
0x14000b34c  call    LogConfig
0x14000b351  mov     ecx, r12d
0x14000b354  mov     dword ptr [rsp+3C0h+Object], r15d
0x14000b359  call    GetHardwareAlgHandle
0x14000b35e  mov     rcx, rax
0x14000b361  mov     dword ptr [rsp+3C0h+StartRoutine], r15d
0x14000b366  mov     rax, cs:g_pHwCipherFunctionTable
0x14000b36d  lea     rdx, [rsp+3C0h+Object]
0x14000b372  mov     [rsp+3C0h+ClientId], rdx
0x14000b377  lea     r8, [rbp+2C0h+var_300]
0x14000b37b  mov     edi, 2B0h
0x14000b380  lea     rdx, aCngchatconfigu; "CngChatConfiguration"
0x14000b387  mov     r9d, edi
0x14000b38a  mov     rax, [rax+10h]
0x14000b38e  call    _guard_dispatch_icall
0x14000b393  test    eax, eax
0x14000b395  js      short loc_14000B3A8
0x14000b397  mov     edx, dword ptr [rsp+3C0h+Object]
0x14000b39b  cmp     edx, edi
0x14000b39d  ja      short loc_14000B3A8
0x14000b39f  lea     rcx, [rbp+2C0h+var_300]
0x14000b3a3  call    ConfigSetChatConfig
0x14000b3a8  lea     rcx, aProvider; "Provider"
0x14000b3af  call    LogConfig
0x14000b3b4  call    ConfigReadRegistry
0x14000b3b9  lea     rcx, aRegistry; "Registry"
0x14000b3c0  call    LogConfig
0x14000b3c5  call    ConfigApplyBounds
0x14000b3ca  mov     rdx, r15
0x14000b3cd  mov     cs:g_mHwThreadsIdle, r15d
0x14000b3d4  mov     edi, r15d
0x14000b3d7  mov     rax, rdx
0x14000b3da  shl     rax, 6
0x14000b3de  mov     ecx, [rax+r13+77E0h]
0x14000b3e6  cmp     edi, ecx
0x14000b3e8  cmova   ecx, edi
0x14000b3eb  add     rdx, r12
0x14000b3ee  mov     edi, ecx
0x14000b3f0  cmp     rdx, 3
0x14000b3f4  jnz     short loc_14000B3D7
0x14000b3f6  lea     rcx, aFinal; "Final"
0x14000b3fd  call    LogConfig
0x14000b402  mov     esi, r15d
0x14000b405  test    edi, edi
0x14000b407  jz      loc_14000B521
0x14000b40d  mov     eax, esi
0x14000b40f  lea     rbx, rva g_hwEngineState[r13]
0x14000b416  imul    r14, rax, 38h ; '8'
0x14000b41a  lea     rcx, rva qword_140007680[r13]
0x14000b421  xor     r8d, r8d; State
0x14000b424  add     rbx, r14
0x14000b427  add     rcx, r14; Event
0x14000b42a  xor     edx, edx; Type
0x14000b42c  mov     [rbx], r15
0x14000b42f  call    cs:__imp_KeInitializeEvent
0x14000b436  nop     dword ptr [rax+rax+00h]
0x14000b43b  lea     rax, HardwareThreadStartFunction
0x14000b442  mov     [rsp+3C0h+StartContext], rbx; StartContext
0x14000b447  xorps   xmm0, xmm0
0x14000b44a  mov     [rsp+3C0h+StartRoutine], rax; StartRoutine
0x14000b44f  xor     r9d, r9d; ProcessHandle
0x14000b452  mov     [rsp+3C0h+ClientId], r15; ClientId
0x14000b457  lea     r8, [rsp+3C0h+ObjectAttributes]; ObjectAttributes
0x14000b45c  mov     [rsp+3C0h+ObjectAttributes.Length], 30h ; '0'
0x14000b464  xor     edx, edx; DesiredAccess
0x14000b466  mov     [rsp+3C0h+ObjectAttributes.RootDirectory], r15
0x14000b46b  lea     rcx, [rsp+3C0h+ThreadHandle]; ThreadHandle
0x14000b470  mov     [rsp+3C0h+ObjectAttributes.Attributes], 200h
0x14000b478  mov     [rsp+3C0h+ObjectAttributes.ObjectName], r15
0x14000b47d  movdqu  xmmword ptr [rsp+3C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b483  call    cs:__imp_PsCreateSystemThread
0x14000b48a  nop     dword ptr [rax+rax+00h]
0x14000b48f  mov     ebx, eax
0x14000b491  test    eax, eax
0x14000b493  js      loc_14000B58B
0x14000b499  mov     rcx, [rsp+3C0h+ThreadHandle]; Handle
0x14000b49e  lea     rax, [rsp+3C0h+Object]
0x14000b4a3  mov     [rsp+3C0h+StartRoutine], r15; HandleInformation
0x14000b4a8  xor     r9d, r9d; AccessMode
0x14000b4ab  xor     r8d, r8d; ObjectType
0x14000b4ae  mov     [rsp+3C0h+ClientId], rax; Object
0x14000b4b3  mov     edx, 1FFFFFh; DesiredAccess
0x14000b4b8  mov     [rsp+3C0h+Object], r15
0x14000b4bd  call    cs:__imp_ObReferenceObjectByHandle
0x14000b4c4  nop     dword ptr [rax+rax+00h]
0x14000b4c9  mov     rcx, [rsp+3C0h+Object]
0x14000b4ce  test    rcx, rcx
0x14000b4d1  jz      loc_14000B5B1
0x14000b4d7  mov     eax, 12h
0x14000b4dc  mov     [r14+r13+7670h], rcx
0x14000b4e4  mov     edx, eax
0x14000b4e6  mov     [r14+r13+7678h], eax
0x14000b4ee  call    cs:__imp_KeSetActualBasePriorityThread
0x14000b4f5  nop     dword ptr [rax+rax+00h]
0x14000b4fa  add     cs:g_actualHardwareThreads, r12d
0x14000b501  mov     ecx, esi
0x14000b503  mov     eax, r12d
0x14000b506  add     esi, r12d
0x14000b509  shl     eax, cl
0x14000b50b  or      cs:g_mHwThreadsIdle, eax
0x14000b511  mov     [r14+r13+7668h], eax
0x14000b519  cmp     esi, edi
0x14000b51b  jb      loc_14000B40D
0x14000b521  mov     rdi, r15
0x14000b524  mov     rax, rdi
0x14000b527  mov     [rbp+2C0h+var_340], r15
0x14000b52b  shl     rax, 5
0x14000b52f  lea     rdx, rva CngChatPowerConfig[r13]
0x14000b536  add     rdx, rax
0x14000b539  mov     [rbp+2C0h+var_338], r15d
0x14000b53d  mov     [rbp+2C0h+var_310], rdx
0x14000b541  lea     rcx, [rbp+2C0h+var_340]
0x14000b545  mov     [rbp+2C0h+var_328], r15
0x14000b549  mov     [rbp+2C0h+var_334], r12d
0x14000b54d  mov     rax, [rdx+8]
0x14000b551  add     rdx, 10h
0x14000b555  mov     [rbp+2C0h+var_330], rax
0x14000b559  lea     rax, EventStartCallback
0x14000b560  mov     [rbp+2C0h+var_320], rax
0x14000b564  lea     rax, EventStopCallback
0x14000b56b  mov     [rbp+2C0h+var_318], rax
0x14000b56f  call    cs:__imp_EACreateAggregateEvent
0x14000b576  nop     dword ptr [rax+rax+00h]
0x14000b57b  add     rdi, r12
0x14000b57e  cmp     rdi, 2
0x14000b582  jnz     short loc_14000B524
0x14000b584  mov     cs:g_fHwProvAvailable, r12b
0x14000b58b  mov     eax, ebx
0x14000b58d  mov     rcx, [rbp+2C0h+var_50]
0x14000b594  xor     rcx, rsp; StackCookie
0x14000b597  call    __security_check_cookie
0x14000b59c  add     rsp, 388h
0x14000b5a3  pop     r15
0x14000b5a5  pop     r14
0x14000b5a7  pop     r13
0x14000b5a9  pop     r12
0x14000b5ab  pop     rdi
0x14000b5ac  pop     rsi
0x14000b5ad  pop     rbx
0x14000b5ae  pop     rbp
0x14000b5af  retn
0x14000b5b1  mov     ebx, 0C00000E5h
0x14000b5b6  jmp     short loc_14000B58B
```
