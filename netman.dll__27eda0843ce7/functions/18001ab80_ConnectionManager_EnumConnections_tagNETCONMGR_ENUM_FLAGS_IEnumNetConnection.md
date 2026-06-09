# ConnectionManager::EnumConnections(tagNETCONMGR_ENUM_FLAGS,IEnumNetConnection * *)

- ea: `0x18001ab80`
- end: `0x18001addd`
- name: `?EnumConnections@ConnectionManager@@UEAAJW4tagNETCONMGR_ENUM_FLAGS@@PEAPEAUIEnumNetConnection@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(ConnectionManager *this, unsigned int, struct IEnumNetConnection **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000538c`
- `0x180019200`
- `0x18001ab80`
- `0x18001b1e8`
- `0x180022a8c`
- `0x180030434`
- `0x18003060c`
- `0x180032c3c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001ad10`
- `ADVAPI32!RegCloseKey` at `0x18001ad10`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18001ad00`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18001ad00`
- `KERNEL32!CreateEventW` at `0x18001ac6f`
- `KERNEL32!CreateEventW` at `0x18001ac6f`
- `KERNEL32!CloseHandle` at `0x18001ad48`
- `KERNEL32!CloseHandle` at `0x18001ad48`
- `KERNEL32!LeaveCriticalSection` at `0x18001ad88`
- `KERNEL32!LeaveCriticalSection` at `0x18001ad88`
- `KERNEL32!EnterCriticalSection` at `0x18001ac38`
- `KERNEL32!EnterCriticalSection` at `0x18001ac38`
- `ntdll!RtlDeregisterWaitEx` at `0x18001ad24`
- `ntdll!RtlDeregisterWaitEx` at `0x18001ad24`
- `ntdll!RtlRegisterWait` at `0x18001acac`
- `ntdll!RtlRegisterWait` at `0x18001acac`

## pseudocode

```c
__int64 __fastcall ConnectionManager::EnumConnections(
        ConnectionManager *this,
        unsigned int a2,
        struct IEnumNetConnection **a3)
{
  PVOID *v6; // rcx
  int Win32Error; // ebx
  __int64 v8; // rdx
  __int64 v9; // rsi
  HANDLE EventW; // rax
  HANDLE *v11; // r15
  NTSTATUS v12; // ebx
  HKEY *v13; // rbx
  LSTATUS v14; // r14d
  NTSTATUS v15; // eax
  __int64 v16; // r8

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    {
      WPP_SF_d(v6[2], 79, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, a2);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( !a3 )
  {
    Win32Error = -2147024809;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      v8 = 80;
LABEL_34:
      WPP_SF_d(v6[2], v8, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, (unsigned int)Win32Error);
      return (unsigned int)Win32Error;
    }
    return (unsigned int)Win32Error;
  }
  v9 = (__int64)this + 48;
  if ( this == (ConnectionManager *)32 )
    v9 = 8;
  EnterCriticalSection((LPCRITICAL_SECTION)v9);
  if ( *((_QWORD *)this + 19) && !*((_QWORD *)this + 21) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_QWORD *)this + 19) )
    goto LABEL_28;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 19) = EventW;
  if ( !EventW )
  {
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error < 0 )
      goto LABEL_30;
    goto LABEL_28;
  }
  v11 = (HANDLE *)((char *)this + 160);
  v12 = RtlRegisterWait(
          (PHANDLE)this + 20,
          EventW,
          ConnectionManager::RegChangeNotifyHandler,
          (char *)this - 32,
          0xFFFFFFFF,
          0);
  if ( v12 >= 0 )
  {
    v13 = (HKEY *)((char *)this + 168);
    v14 = HrRegOpenKeyEx(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Network\\Connections",
            0x20019u,
            (HKEY *)this + 21);
    if ( v14 >= 0 )
    {
      v14 = RegNotifyChangeKeyValue(*v13, 0, 4u, *((HANDLE *)this + 19), 1);
      if ( v14 >= 0 )
        goto LABEL_28;
      RegCloseKey(*v13);
      *v13 = 0;
    }
    v15 = RtlDeregisterWaitEx(*v11, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *v11 = 0;
    Win32Error = v15 | 0x10000000;
    if ( v15 >= 0 )
      Win32Error = v14;
  }
  else
  {
    Win32Error = v12 | 0x10000000;
  }
  if ( Win32Error < 0 )
  {
    CloseHandle(*((HANDLE *)this + 19));
    *((_QWORD *)this + 19) = 0;
    goto LABEL_30;
  }
LABEL_28:
  Win32Error = ConnectionManager::HrEnsureClassManagersLoaded((ConnectionManager *)((char *)this - 32));
  if ( Win32Error >= 0 )
    Win32Error = ConnectionManagerEnumConnection::CreateInstance(a2, (char *)this + 96, v16, a3);
LABEL_30:
  LeaveCriticalSection((LPCRITICAL_SECTION)v9);
  if ( Win32Error < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 81;
      goto LABEL_34;
    }
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x18001ab80  mov     [rsp+arg_18], rbx
0x18001ab85  push    rbp
0x18001ab86  push    rsi
0x18001ab87  push    rdi
0x18001ab88  push    r12
0x18001ab8a  push    r13
0x18001ab8c  push    r14
0x18001ab8e  push    r15
0x18001ab90  sub     rsp, 30h
0x18001ab94  mov     r12, r8
0x18001ab97  mov     r13d, edx
0x18001ab9a  mov     rdi, rcx
0x18001ab9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aba4  lea     rsi, WPP_GLOBAL_Control
0x18001abab  lea     rbp, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001abb2  mov     ebx, 8
0x18001abb7  cmp     rcx, rsi
0x18001abba  jz      short loc_18001ABFC
0x18001abbc  test    [rcx+1Ch], bl
0x18001abbf  jz      short loc_18001ABD7
0x18001abc1  mov     rcx, [rcx+10h]
0x18001abc5  lea     edx, [rbx+46h]
0x18001abc8  mov     r8, rbp
0x18001abcb  call    WPP_SF_
0x18001abd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abd7  cmp     rcx, rsi
0x18001abda  jz      short loc_18001ABFC
0x18001abdc  test    [rcx+1Ch], bl
0x18001abdf  jz      short loc_18001ABFC
0x18001abe1  mov     rcx, [rcx+10h]
0x18001abe5  mov     edx, 4Fh ; 'O'
0x18001abea  mov     r9d, r13d
0x18001abed  mov     r8, rbp
0x18001abf0  call    WPP_SF_d
0x18001abf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abfc  test    r12, r12
0x18001abff  jnz     short loc_18001AC26
0x18001ac01  mov     ebx, 80070057h
0x18001ac06  cmp     rcx, rsi
0x18001ac09  jz      loc_18001ADC3
0x18001ac0f  test    byte ptr [rcx+1Ch], 1
0x18001ac13  jz      loc_18001ADC3
0x18001ac19  lea     edx, [r12+50h]
0x18001ac1e  mov     r8, rbp
0x18001ac21  jmp     loc_18001ADB7
0x18001ac26  lea     rbp, [rdi-20h]
0x18001ac2a  test    rbp, rbp
0x18001ac2d  lea     rsi, [rdi+30h]
0x18001ac31  cmovz   rsi, rbx
0x18001ac35  mov     rcx, rsi; lpCriticalSection
0x18001ac38  call    cs:__imp_EnterCriticalSection
0x18001ac3e  cmp     qword ptr [rbp+0B8h], 0
0x18001ac46  jz      short loc_18001AC57
0x18001ac48  cmp     qword ptr [rdi+0A8h], 0
0x18001ac50  jnz     short loc_18001AC57
0x18001ac52  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ac57  cmp     qword ptr [rdi+98h], 0
0x18001ac5f  jnz     loc_18001AD66
0x18001ac65  xor     r9d, r9d; lpName
0x18001ac68  xor     r8d, r8d; bInitialState
0x18001ac6b  xor     edx, edx; bManualReset
0x18001ac6d  xor     ecx, ecx; lpEventAttributes
0x18001ac6f  call    cs:__imp_CreateEventW
0x18001ac75  mov     [rdi+98h], rax
0x18001ac7c  test    rax, rax
0x18001ac7f  jz      loc_18001AD5B
0x18001ac85  lea     r15, [rdi+0A0h]
0x18001ac8c  mov     [rsp+68h+ulFlags], 0; ulFlags
0x18001ac94  mov     rcx, r15; phNewWaitObject
0x18001ac97  mov     [rsp+68h+ulMilliseconds], 0FFFFFFFFh; ulMilliseconds
0x18001ac9f  mov     r9, rbp; pvContext
0x18001aca2  lea     r8, ?RegChangeNotifyHandler@ConnectionManager@@CAXPEAXE@Z; Callback
0x18001aca9  mov     rdx, rax; hObject
0x18001acac  call    cs:__imp_RtlRegisterWait
0x18001acb2  mov     ebx, eax
0x18001acb4  test    eax, eax
0x18001acb6  jns     short loc_18001ACBE
0x18001acb8  bts     ebx, 1Ch
0x18001acbc  jmp     short loc_18001AD3D
0x18001acbe  lea     rbx, [rdi+0A8h]
0x18001acc5  mov     r8d, 20019h; unsigned int
0x18001accb  mov     r9, rbx; HKEY *
0x18001acce  lea     rdx, ?c_szRegKeyClassManagers@@3QBGB; "System\\CurrentControlSet\\Control\\Net"...
0x18001acd5  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001acdc  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18001ace1  mov     r14d, eax
0x18001ace4  test    eax, eax
0x18001ace6  js      short loc_18001AD1D
0x18001ace8  mov     r9, [rdi+98h]; hEvent
0x18001acef  xor     edx, edx; bWatchSubtree
0x18001acf1  mov     rcx, [rbx]; hKey
0x18001acf4  mov     [rsp+68h+ulMilliseconds], 1; fAsynchronous
0x18001acfc  lea     r8d, [rdx+4]; dwNotifyFilter
0x18001ad00  call    cs:__imp_RegNotifyChangeKeyValue
0x18001ad06  mov     r14d, eax
0x18001ad09  test    eax, eax
0x18001ad0b  jns     short loc_18001AD66
0x18001ad0d  mov     rcx, [rbx]; hKey
0x18001ad10  call    cs:__imp_RegCloseKey
0x18001ad16  mov     qword ptr [rbx], 0
0x18001ad1d  mov     rcx, [r15]; hWaitHandle
0x18001ad20  or      rdx, 0FFFFFFFFFFFFFFFFh; hCompletionEvent
0x18001ad24  call    cs:__imp_RtlDeregisterWaitEx
0x18001ad2a  mov     ebx, eax
0x18001ad2c  mov     qword ptr [r15], 0
0x18001ad33  bts     ebx, 1Ch
0x18001ad37  test    eax, eax
0x18001ad39  cmovns  ebx, r14d
0x18001ad3d  test    ebx, ebx
0x18001ad3f  jns     short loc_18001AD66
0x18001ad41  mov     rcx, [rdi+98h]; hObject
0x18001ad48  call    cs:__imp_CloseHandle
0x18001ad4e  mov     qword ptr [rdi+98h], 0
0x18001ad59  jmp     short loc_18001AD85
0x18001ad5b  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001ad60  mov     ebx, eax
0x18001ad62  test    eax, eax
0x18001ad64  js      short loc_18001AD85
0x18001ad66  mov     rcx, rbp; this
0x18001ad69  call    ?HrEnsureClassManagersLoaded@ConnectionManager@@AEAAJXZ; ConnectionManager::HrEnsureClassManagersLoaded(void)
0x18001ad6e  mov     ebx, eax
0x18001ad70  test    eax, eax
0x18001ad72  js      short loc_18001AD85
0x18001ad74  lea     rdx, [rdi+60h]
0x18001ad78  mov     r9, r12
0x18001ad7b  mov     ecx, r13d
0x18001ad7e  call    ?CreateInstance@ConnectionManagerEnumConnection@@SAJW4tagNETCONMGR_ENUM_FLAGS@@AEBV?$map@U_GUID@@PEAUINetConnectionManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@4@@std@@AEBU_GUID@@PEAPEAX@Z; ConnectionManagerEnumConnection::CreateInstance(tagNETCONMGR_ENUM_FLAGS,std::map<_GUID,INetConnectionManager *> const &,_GUID const &,void * *)
0x18001ad83  mov     ebx, eax
0x18001ad85  mov     rcx, rsi; lpCriticalSection
0x18001ad88  call    cs:__imp_LeaveCriticalSection
0x18001ad8e  test    ebx, ebx
0x18001ad90  jns     short loc_18001ADC3
0x18001ad92  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad99  lea     rax, WPP_GLOBAL_Control
0x18001ada0  cmp     rcx, rax
0x18001ada3  jz      short loc_18001ADC3
0x18001ada5  test    byte ptr [rcx+1Ch], 1
0x18001ada9  jz      short loc_18001ADC3
0x18001adab  mov     edx, 51h ; 'Q'
0x18001adb0  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001adb7  mov     rcx, [rcx+10h]
0x18001adbb  mov     r9d, ebx
0x18001adbe  call    WPP_SF_d
0x18001adc3  mov     eax, ebx
0x18001adc5  mov     rbx, [rsp+68h+arg_18]
0x18001adcd  add     rsp, 30h
0x18001add1  pop     r15
0x18001add3  pop     r14
0x18001add5  pop     r13
0x18001add7  pop     r12
0x18001add9  pop     rdi
0x18001adda  pop     rsi
0x18001addb  pop     rbp
0x18001addc  retn
```
