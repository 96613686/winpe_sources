# ContactXferMonitor(RA_FILE_RECV_CLIENT_CONTEXT *,RAFX_STATUS)

- ea: `0x14002e288`
- end: `0x14002e447`
- name: `?ContactXferMonitor@@YAJPEAURA_FILE_RECV_CLIENT_CONTEXT@@W4RAFX_STATUS@@@Z`
- size: `447`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14002e288`
- `0x14002ea50`
- `0x14002f620`

## callees

- `0x14002e288`
- `0x140034ce4`
- `0x140035888`
- `0x1400383c8`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x14002e32c`
- `KERNEL32!MoveFileExW` at `0x14002e32c`
- `KERNEL32!SetEvent` at `0x14002e380`
- `KERNEL32!SetEvent` at `0x14002e380`
- `KERNEL32!CreateThread` at `0x14002e3cc`
- `KERNEL32!CreateThread` at `0x14002e3cc`
- `KERNEL32!CloseHandle` at `0x14002e414`
- `KERNEL32!CloseHandle` at `0x14002e414`
- `OLEAUT32!__imp_SysFreeString` at `0x14002e428`
- `OLEAUT32!__imp_SysFreeString` at `0x14002e428`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ContactXferMonitor(LPCWSTR *a1, int a2)
{
  unsigned int v3; // edi
  OLECHAR *v4; // rbx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  signed int DirectoryAsBSTR; // eax
  CEventLogger *v10; // rcx
  int v11; // ecx
  CEventLogger *v12; // rdx
  HANDLE Thread; // rax
  CEventLogger *v14; // rcx
  LPCWSTR lpNewFileName; // [rsp+50h] [rbp+18h] BYREF

  v3 = 0;
  v4 = 0;
  lpNewFileName = 0;
  v5 = a2 - 6;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( !v6 || (v7 = v6 - 1) == 0 || (v8 = v7 - 2) == 0 )
    {
      v12 = _AtlModule;
LABEL_15:
      SetEvent(*((HANDLE *)v12 + 107));
      goto LABEL_20;
    }
    if ( v8 != 4 )
      return v3;
    DirectoryAsBSTR = GetDirectoryAsBSTR(0, (unsigned __int16 **)&lpNewFileName, L"RaRemoteContact");
    v3 = DirectoryAsBSTR;
    if ( DirectoryAsBSTR < 0 )
    {
      CEventLogger::LogError(
        v10,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
        0x41Au,
        L"ContactXferMonitor",
        DirectoryAsBSTR);
      v4 = (OLECHAR *)lpNewFileName;
      goto LABEL_20;
    }
    v4 = (OLECHAR *)lpNewFileName;
    if ( !MoveFileExW(*a1, lpNewFileName, 3u) )
      ContactXferMonitor(a1, 7);
    v11 = 0;
  }
  else
  {
    v11 = 1;
  }
  v12 = _AtlModule;
  if ( *(_QWORD *)(*((_QWORD *)_AtlModule + 104) + 208LL) )
  {
    if ( !v11 )
    {
      CSqmManager::StartTimer((CEventLogger *)((char *)_AtlModule + 496), 0x3039u);
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SendContactInfoThread, (LPVOID)1, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
      }
      else
      {
        v3 = -2147467259;
        CEventLogger::LogError(
          v14,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
          0x448u,
          L"ContactXferMonitor",
          0x80004005);
      }
    }
    goto LABEL_20;
  }
  if ( !v11 )
    goto LABEL_15;
LABEL_20:
  if ( v4 )
    SysFreeString(v4);
  return v3;
}

```

## disassembly

```asm
0x14002e288  mov     rax, rsp
0x14002e28b  mov     [rax+8], rbx
0x14002e28f  mov     [rax+10h], rsi
0x14002e293  push    rdi
0x14002e294  sub     rsp, 30h
0x14002e298  mov     rsi, rcx
0x14002e29b  xor     edi, edi
0x14002e29d  xor     ebx, ebx
0x14002e29f  mov     [rax+18h], rbx
0x14002e2a3  sub     edx, 6
0x14002e2a6  jz      loc_14002E354
0x14002e2ac  sub     edx, 1
0x14002e2af  jz      loc_14002E34B
0x14002e2b5  sub     edx, 1
0x14002e2b8  jz      loc_14002E34B
0x14002e2be  sub     edx, 2
0x14002e2c1  jz      loc_14002E34B
0x14002e2c7  cmp     edx, 4
0x14002e2ca  jnz     loc_14002E434
0x14002e2d0  lea     r8, aRaremotecontac; "RaRemoteContact"
0x14002e2d7  lea     rdx, [rax+18h]; unsigned __int16 **
0x14002e2db  xor     ecx, ecx; csidl
0x14002e2dd  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x14002e2e2  mov     edi, eax
0x14002e2e4  test    eax, eax
0x14002e2e6  jns     short loc_14002E31B
0x14002e2e8  mov     dword ptr [rsp+38h+lpThreadId], eax; unsigned int
0x14002e2ec  lea     rax, aContactxfermon; "ContactXferMonitor"
0x14002e2f3  mov     qword ptr [rsp+38h+dwCreationFlags], rax; unsigned __int16 *
0x14002e2f8  mov     r9d, 41Ah; unsigned int
0x14002e2fe  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\ui\\filexfer.cpp"
0x14002e305  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002e30c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002e311  mov     rbx, [rsp+38h+lpNewFileName]
0x14002e316  jmp     loc_14002E420
0x14002e31b  mov     r8d, 3; dwFlags
0x14002e321  mov     rbx, [rsp+38h+lpNewFileName]
0x14002e326  mov     rdx, rbx; lpNewFileName
0x14002e329  mov     rcx, [rsi]; lpExistingFileName
0x14002e32c  call    cs:__imp_MoveFileExW
0x14002e333  nop     dword ptr [rax+rax+00h]
0x14002e338  test    eax, eax
0x14002e33a  jnz     short loc_14002E347
0x14002e33c  lea     edx, [rax+7]
0x14002e33f  mov     rcx, rsi
0x14002e342  call    ?ContactXferMonitor@@YAJPEAURA_FILE_RECV_CLIENT_CONTEXT@@W4RAFX_STATUS@@@Z; ContactXferMonitor(RA_FILE_RECV_CLIENT_CONTEXT *,RAFX_STATUS)
0x14002e347  xor     ecx, ecx
0x14002e349  jmp     short loc_14002E359
0x14002e34b  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e352  jmp     short loc_14002E379
0x14002e354  mov     ecx, 1
0x14002e359  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e360  mov     rax, [rdx+340h]
0x14002e367  cmp     qword ptr [rax+0D0h], 0
0x14002e36f  jnz     short loc_14002E391
0x14002e371  test    ecx, ecx
0x14002e373  jnz     loc_14002E420
0x14002e379  mov     rcx, [rdx+358h]; hEvent
0x14002e380  call    cs:__imp_SetEvent
0x14002e387  nop     dword ptr [rax+rax+00h]
0x14002e38c  jmp     loc_14002E420
0x14002e391  test    ecx, ecx
0x14002e393  jnz     loc_14002E420
0x14002e399  lea     rcx, [rdx+1F0h]; this
0x14002e3a0  mov     edx, 3039h; unsigned int
0x14002e3a5  call    ?StartTimer@CSqmManager@@QEAAXK@Z; CSqmManager::StartTimer(ulong)
0x14002e3aa  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x14002e3b3  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14002e3bb  mov     r9d, 1; lpParameter
0x14002e3c1  lea     r8, ?SendContactInfoThread@@YAKPEAX@Z; lpStartAddress
0x14002e3c8  xor     edx, edx; dwStackSize
0x14002e3ca  xor     ecx, ecx; lpThreadAttributes
0x14002e3cc  call    cs:__imp_CreateThread
0x14002e3d3  nop     dword ptr [rax+rax+00h]
0x14002e3d8  test    rax, rax
0x14002e3db  jnz     short loc_14002E411
0x14002e3dd  mov     edi, 80004005h
0x14002e3e2  mov     dword ptr [rsp+38h+lpThreadId], 80004005h; unsigned int
0x14002e3ea  lea     rax, aContactxfermon; "ContactXferMonitor"
0x14002e3f1  mov     qword ptr [rsp+38h+dwCreationFlags], rax; unsigned __int16 *
0x14002e3f6  mov     r9d, 448h; unsigned int
0x14002e3fc  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\ui\\filexfer.cpp"
0x14002e403  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002e40a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002e40f  jmp     short loc_14002E420
0x14002e411  mov     rcx, rax; hObject
0x14002e414  call    cs:__imp_CloseHandle
0x14002e41b  nop     dword ptr [rax+rax+00h]
0x14002e420  test    rbx, rbx
0x14002e423  jz      short loc_14002E434
0x14002e425  mov     rcx, rbx; bstrString
0x14002e428  call    cs:__imp_SysFreeString
0x14002e42f  nop     dword ptr [rax+rax+00h]
0x14002e434  mov     eax, edi
0x14002e436  mov     rbx, [rsp+38h+arg_0]
0x14002e43b  mov     rsi, [rsp+38h+arg_8]
0x14002e440  add     rsp, 30h
0x14002e444  pop     rdi
0x14002e445  retn
```
