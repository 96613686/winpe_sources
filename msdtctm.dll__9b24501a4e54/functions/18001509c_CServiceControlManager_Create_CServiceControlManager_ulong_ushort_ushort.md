# CServiceControlManager::Create(CServiceControlManager * *,ulong,ushort *,ushort *)

- ea: `0x18001509c`
- end: `0x18001522a`
- name: `?Create@CServiceControlManager@@SAJPEAPEAV1@KPEAG1@Z`
- size: `398`
- prototype: `__int64 __fastcall(struct CServiceControlManager **, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180014b94`

## callees

- `0x18001509c`
- `0x180015230`
- `0x1800152f8`
- `0x1800240b0`
- `0x1800240f0`
- `0x180085f44`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180015169`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180015169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015121`
- `msvcrt!fprintf` at `0x1800151cc`
- `msvcrt!fprintf` at `0x1800151cc`
- `msvcrt!fclose` at `0x1800151de`
- `msvcrt!fclose` at `0x1800151de`
- `msvcrt!fflush` at `0x1800151d5`
- `msvcrt!fflush` at `0x1800151d5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001510e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001510e`

## string_xrefs

- `0x180015136`: `com\complus\dtc\shared\util\scm.cpp`
- `0x180015146`: `OpenSCManagerW call failed`
- `0x1800151c0`: `%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n`
- `0x180015181`: `CServiceControlManager::InternalInit call failed`

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
  FILE *v11; // rsi
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-48h] BYREF

  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  v6 = (struct CServiceControlManager *)operator new(0x10u);
  *(_QWORD *)&SystemTime.wYear = v6;
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *(_DWORD *)v6 = 1;
  *((_QWORD *)v6 + 1) = 0;
  v8 = 0;
  v9 = OpenSCManagerW(0, 0, 0x80000000);
  *((_QWORD *)v7 + 1) = v9;
  if ( v9 )
    goto LABEL_10;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  TraceFile(v8, "OpenSCManagerW call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x3Bu);
  if ( v8 >= 0 )
  {
LABEL_10:
    *a1 = v7;
    _InterlockedIncrement((volatile signed __int32 *)v7);
  }
  else
  {
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    v11 = OpenTraceFile();
    if ( v11 )
    {
      fprintf(
        v11,
        "%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n",
        SystemTime.wMonth,
        SystemTime.wDay,
        SystemTime.wYear,
        SystemTime.wHour,
        SystemTime.wMinute,
        v8,
        "CServiceControlManager::InternalInit call failed",
        "com\\complus\\dtc\\shared\\util\\scm.cpp",
        106);
      fflush(v11);
      fclose(v11);
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
  {
    CServiceControlManager::~CServiceControlManager(v7);
    operator delete(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001509c  push    rbx
0x18001509e  push    rbp
0x18001509f  push    rsi
0x1800150a0  push    rdi
0x1800150a1  sub     rsp, 88h
0x1800150a8  mov     rax, cs:__security_cookie
0x1800150af  xor     rax, rsp
0x1800150b2  mov     [rsp+0A8h+var_38], rax
0x1800150b7  mov     rsi, rcx
0x1800150ba  test    rcx, rcx
0x1800150bd  jnz     short loc_1800150C9
0x1800150bf  mov     eax, 80070057h
0x1800150c4  jmp     loc_180015211
0x1800150c9  mov     qword ptr [rcx], 0
0x1800150d0  mov     ecx, 10h; Size
0x1800150d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800150da  mov     qword ptr [rsp+0A8h+SystemTime.wYear], rax
0x1800150df  mov     rbx, rax
0x1800150e2  test    rax, rax
0x1800150e5  jz      loc_18001520C
0x1800150eb  mov     dword ptr [rax], 1
0x1800150f1  mov     qword ptr [rax+8], 0
0x1800150f9  test    rax, rax
0x1800150fc  jz      loc_18001520C
0x180015102  xor     edx, edx; lpDatabaseName
0x180015104  xor     ecx, ecx; lpMachineName
0x180015106  mov     r8d, 80000000h; dwDesiredAccess
0x18001510c  xor     edi, edi
0x18001510e  call    cs:__imp_OpenSCManagerW
0x180015114  mov     [rbx+8], rax
0x180015118  test    rax, rax
0x18001511b  jnz     loc_1800151E6
0x180015121  call    cs:__imp_GetLastError
0x180015127  mov     edi, eax
0x180015129  test    eax, eax
0x18001512b  jle     short loc_180015136
0x18001512d  movzx   edi, ax
0x180015130  or      edi, 80070000h
0x180015136  lea     rbp, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x18001513d  mov     r9d, 3Bh ; ';'; unsigned int
0x180015143  mov     r8, rbp; char *
0x180015146  lea     rdx, aOpenscmanagerw; "OpenSCManagerW call failed"
0x18001514d  mov     ecx, edi; int
0x18001514f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180015154  test    edi, edi
0x180015156  jns     loc_1800151E6
0x18001515c  xorps   xmm0, xmm0
0x18001515f  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180015164  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x180015169  call    cs:__imp_GetLocalTime
0x18001516f  call    ?OpenTraceFile@@YAPEAU_iobuf@@XZ; OpenTraceFile(void)
0x180015174  mov     rsi, rax
0x180015177  test    rax, rax
0x18001517a  jz      short loc_1800151EC
0x18001517c  movzx   ecx, [rsp+0A8h+SystemTime.wMinute]
0x180015181  lea     rax, aCservicecontro_1; "CServiceControlManager::InternalInit ca"...
0x180015188  movzx   edx, [rsp+0A8h+SystemTime.wHour]
0x18001518d  movzx   r10d, [rsp+0A8h+SystemTime.wYear]
0x180015193  movzx   r9d, [rsp+0A8h+SystemTime.wDay]
0x180015199  movzx   r8d, [rsp+0A8h+SystemTime.wMonth]
0x18001519f  mov     [rsp+0A8h+var_58], 6Ah ; 'j'
0x1800151a7  mov     [rsp+0A8h+var_60], rbp
0x1800151ac  mov     [rsp+0A8h+var_68], rax
0x1800151b1  mov     [rsp+0A8h+var_70], edi
0x1800151b5  mov     [rsp+0A8h+var_78], ecx
0x1800151b9  mov     rcx, rsi; Stream
0x1800151bc  mov     [rsp+0A8h+var_80], edx
0x1800151c0  lea     rdx, Format; "%02ld-%02ld-%04ld %02ld:%02ld : DTC Ins"...
0x1800151c7  mov     [rsp+0A8h+var_88], r10d
0x1800151cc  call    cs:__imp_fprintf
0x1800151d2  mov     rcx, rsi; Stream
0x1800151d5  call    cs:__imp_fflush
0x1800151db  mov     rcx, rsi; Stream
0x1800151de  call    cs:__imp_fclose
0x1800151e4  jmp     short loc_1800151EC
0x1800151e6  mov     [rsi], rbx
0x1800151e9  lock inc dword ptr [rbx]
0x1800151ec  or      edx, 0FFFFFFFFh
0x1800151ef  lock xadd [rbx], edx
0x1800151f3  cmp     edx, 1
0x1800151f6  jnz     short loc_180015208
0x1800151f8  mov     rcx, rbx; this
0x1800151fb  call    ??1CServiceControlManager@@IEAA@XZ; CServiceControlManager::~CServiceControlManager(void)
0x180015200  mov     rcx, rbx; Block
0x180015203  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015208  mov     eax, edi
0x18001520a  jmp     short loc_180015211
0x18001520c  mov     eax, 8007000Eh
0x180015211  mov     rcx, [rsp+0A8h+var_38]
0x180015216  xor     rcx, rsp; StackCookie
0x180015219  call    __security_check_cookie
0x18001521e  add     rsp, 88h
0x180015225  pop     rdi
0x180015226  pop     rsi
0x180015227  pop     rbp
0x180015228  pop     rbx
0x180015229  retn
```
