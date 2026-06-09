# CServiceControlManager::Create(CServiceControlManager * *,ulong,ushort *,ushort *)

- ea: `0x18007995c`
- end: `0x180079a45`
- name: `?Create@CServiceControlManager@@SAJPEAPEAV1@KPEAG1@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct CServiceControlManager **, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x180011ac0`
- `0x18001d138`
- `0x18007995c`
- `0x180079a8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800799cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800799cd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800799be`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800799be`

## string_xrefs

- `0x1800799e8`: `com\complus\dtc\shared\util\scm.cpp`
- `0x180079a07`: `com\complus\dtc\shared\util\scm.cpp`
- `0x1800799ef`: `OpenSCManagerW call failed`
- `0x180079a0e`: `CServiceControlManager::InternalInit call failed`

## pseudocode

```c
__int64 __fastcall CServiceControlManager::Create(
        struct CServiceControlManager **a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  struct CServiceControlManager *v6; // rax
  struct CServiceControlManager *v7; // rbx
  signed int v8; // edi
  SC_HANDLE v9; // rax
  signed int LastError; // eax

  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  v6 = (struct CServiceControlManager *)operator new(0x10u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *(_DWORD *)v6 = 1;
  *((_QWORD *)v6 + 1) = 0;
  v8 = 0;
  v9 = OpenSCManagerW(0, 0, 0x80000000);
  *((_QWORD *)v7 + 1) = v9;
  if ( v9 )
    goto LABEL_9;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  TraceFile(v8, "OpenSCManagerW call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x3Bu);
  if ( v8 >= 0 )
  {
LABEL_9:
    *a1 = v7;
    _InterlockedIncrement((volatile signed __int32 *)v7);
  }
  else
  {
    TraceFile(v8, "CServiceControlManager::InternalInit call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x6Au);
  }
  CServiceControlManager::Release(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007995c  mov     [rsp+arg_0], rbx
0x180079961  mov     [rsp+arg_8], rsi
0x180079966  push    rdi
0x180079967  sub     rsp, 20h
0x18007996b  mov     rsi, rcx
0x18007996e  test    rcx, rcx
0x180079971  jnz     short loc_18007997D
0x180079973  mov     eax, 80070057h
0x180079978  jmp     loc_180079A35
0x18007997d  mov     qword ptr [rcx], 0
0x180079984  mov     ecx, 10h; Size
0x180079989  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007998e  mov     [rsp+28h+arg_18], rax
0x180079993  mov     rbx, rax
0x180079996  test    rax, rax
0x180079999  jz      loc_180079A30
0x18007999f  mov     dword ptr [rax], 1
0x1800799a5  mov     qword ptr [rax+8], 0
0x1800799ad  test    rax, rax
0x1800799b0  jz      short loc_180079A30
0x1800799b2  xor     edx, edx; lpDatabaseName
0x1800799b4  xor     ecx, ecx; lpMachineName
0x1800799b6  mov     r8d, 80000000h; dwDesiredAccess
0x1800799bc  xor     edi, edi
0x1800799be  call    cs:__imp_OpenSCManagerW
0x1800799c4  mov     [rbx+8], rax
0x1800799c8  test    rax, rax
0x1800799cb  jnz     short loc_180079A1E
0x1800799cd  call    cs:__imp_GetLastError
0x1800799d3  mov     edi, eax
0x1800799d5  test    eax, eax
0x1800799d7  jle     short loc_1800799E2
0x1800799d9  movzx   edi, ax
0x1800799dc  or      edi, 80070000h
0x1800799e2  mov     r9d, 3Bh ; ';'; unsigned int
0x1800799e8  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x1800799ef  lea     rdx, aOpenscmanagerw_0; "OpenSCManagerW call failed"
0x1800799f6  mov     ecx, edi; int
0x1800799f8  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800799fd  test    edi, edi
0x1800799ff  jns     short loc_180079A1E
0x180079a01  mov     r9d, 6Ah ; 'j'; unsigned int
0x180079a07  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x180079a0e  lea     rdx, aCservicecontro_1; "CServiceControlManager::InternalInit ca"...
0x180079a15  mov     ecx, edi; int
0x180079a17  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180079a1c  jmp     short loc_180079A24
0x180079a1e  mov     [rsi], rbx
0x180079a21  lock inc dword ptr [rbx]
0x180079a24  mov     rcx, rbx; this
0x180079a27  call    ?Release@CServiceControlManager@@QEAAKXZ; CServiceControlManager::Release(void)
0x180079a2c  mov     eax, edi
0x180079a2e  jmp     short loc_180079A35
0x180079a30  mov     eax, 8007000Eh
0x180079a35  mov     rbx, [rsp+28h+arg_0]
0x180079a3a  mov     rsi, [rsp+28h+arg_8]
0x180079a3f  add     rsp, 20h
0x180079a43  pop     rdi
0x180079a44  retn
```
