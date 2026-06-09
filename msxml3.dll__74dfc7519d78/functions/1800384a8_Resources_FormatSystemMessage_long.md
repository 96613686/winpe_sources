# Resources::FormatSystemMessage(long)

- ea: `0x1800384a8`
- end: `0x1800386a0`
- name: `?FormatSystemMessage@Resources@@SAPEAVString@@J@Z`
- size: `504`
- prototype: `struct String *__fastcall(DWORD dwMessageId)`
- caller_count: `10`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180037ec4`
- `0x180046640`
- `0x18004aef4`
- `0x180064230`
- `0x180088b80`
- `0x180094070`
- `0x1800ae4f0`
- `0x1800e7d04`
- `0x1800f7ee0`
- `0x1800fa3c8`

## callees

- `0x18000912c`
- `0x18001f080`
- `0x1800222c0`
- `0x1800384a8`
- `0x180052070`
- `0x180064034`
- `0x180064ab0`
- `0x180065384`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180038600`
- `msvcrt!_resetstkoflw` at `0x180038600`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038653`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038653`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800385ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800385ee`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800384fd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800384fd`

## string_xrefs

- `0x180038517`: `URLMON.DLL`
- `0x180038595`: `URLMON.DLL`
- `0x180038533`: `WININET.DLL`
- `0x18003856c`: `WINHTTP.DLL`

## pseudocode

```c
struct String *__fastcall Resources::FormatSystemMessage(DWORD dwMessageId)
{
  WCHAR *lpBuffer; // rax
  WCHAR *v3; // rbx
  DWORD v5; // eax
  __int64 v6; // r9
  __int64 v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // r9
  unsigned int v10; // eax
  __int64 v11; // r9
  unsigned int v12; // eax
  struct String *v13; // rax
  struct String *v14; // rax
  struct String *v15; // rdi

  lpBuffer = (WCHAR *)new_array_ne<unsigned short>(4096);
  v3 = lpBuffer;
  if ( !lpBuffer )
    return (struct String *)&String::s_cstrEmpty;
  v5 = FormatMessageW(0x1000u, 0, dwMessageId, 0x400u, lpBuffer, 0x1000u, 0);
  v7 = v5;
  if ( !v5 )
  {
    v8 = Resources::SafeFormatMessage(L"URLMON.DLL", dwMessageId, v3, v6, 1);
    v7 = v8;
    if ( !v8 )
    {
      v10 = Resources::SafeFormatMessage(L"WININET.DLL", dwMessageId, v3, v9, 1);
      v7 = v10;
      if ( !v10 )
      {
        if ( (dwMessageId & 0x1FFF0000) != 0x70000
          || (unsigned int)(unsigned __int16)dwMessageId - 12001 > 0xC0
          || (v12 = Resources::SafeFormatMessage(L"WINHTTP.DLL", dwMessageId, v3, v11, 1), (v7 = v12) == 0) )
        {
          if ( dwMessageId + 2146697216 <= 0x3FF )
            v7 = (unsigned int)Resources::SafeFormatMessage(L"URLMON.DLL", dwMessageId, v3, v11, 0);
        }
      }
    }
  }
  if ( (_DWORD)v7 )
  {
    v3[v7] = 0;
    v13 = String::newString(v3);
  }
  else
  {
    v14 = String::newString(dwMessageId);
    v13 = Resources::FormatMessageW(-1072897270, v14, 0, 0, 0);
  }
  v15 = v13;
  MemFreeObject(v3);
  return v15;
}

```

## disassembly

```asm
0x1800384a8  mov     [rsp+arg_0], rbx
0x1800384ad  push    rdi
0x1800384ae  sub     rsp, 50h
0x1800384b2  mov     edi, ecx
0x1800384b4  mov     ecx, 1000h
0x1800384b9  call    ??$new_array_ne@G@@YAPEAG_J@Z; new_array_ne<ushort>(__int64)
0x1800384be  mov     rbx, rax
0x1800384c1  mov     [rsp+58h+arg_8], rax
0x1800384c6  test    rax, rax
0x1800384c9  jnz     short loc_1800384D7
0x1800384cb  lea     rax, ?s_cstrEmpty@String@@2V_CodebaseString@@B; _CodebaseString const String::s_cstrEmpty
0x1800384d2  jmp     loc_180038695
0x1800384d7  mov     [rsp+58h+Arguments], 0; Arguments
0x1800384e0  mov     [rsp+58h+nSize], 1000h; nSize
0x1800384e8  mov     [rsp+58h+lpBuffer], rbx; lpBuffer
0x1800384ed  mov     r9d, 400h; dwLanguageId
0x1800384f3  mov     r8d, edi; dwMessageId
0x1800384f6  xor     edx, edx; lpSource
0x1800384f8  mov     ecx, 1000h; dwFlags
0x1800384fd  call    cs:__imp_FormatMessageW
0x180038503  mov     ecx, eax
0x180038505  test    eax, eax
0x180038507  jnz     loc_1800385A3
0x18003850d  mov     byte ptr [rsp+58h+lpBuffer], 1; bool
0x180038512  mov     r8, rbx; lpBuffer
0x180038515  mov     edx, edi; dwMessageId
0x180038517  lea     rcx, aUrlmonDll_0; "URLMON.DLL"
0x18003851e  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x180038523  mov     ecx, eax
0x180038525  test    eax, eax
0x180038527  jnz     short loc_1800385A3
0x180038529  mov     byte ptr [rsp+58h+lpBuffer], 1; bool
0x18003852e  mov     r8, rbx; lpBuffer
0x180038531  mov     edx, edi; dwMessageId
0x180038533  lea     rcx, aWininetDll_0; "WININET.DLL"
0x18003853a  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x18003853f  mov     ecx, eax
0x180038541  test    eax, eax
0x180038543  jnz     short loc_1800385A3
0x180038545  mov     eax, edi
0x180038547  and     eax, 1FFF0000h
0x18003854c  cmp     eax, 70000h
0x180038551  jnz     short loc_18003857E
0x180038553  movzx   eax, di
0x180038556  sub     eax, 2EE1h
0x18003855b  cmp     eax, 0C0h
0x180038560  ja      short loc_18003857E
0x180038562  mov     byte ptr [rsp+58h+lpBuffer], 1; bool
0x180038567  mov     r8, rbx; lpBuffer
0x18003856a  mov     edx, edi; dwMessageId
0x18003856c  lea     rcx, aWinhttpDll_0; "WINHTTP.DLL"
0x180038573  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x180038578  mov     ecx, eax
0x18003857a  test    eax, eax
0x18003857c  jnz     short loc_1800385A3
0x18003857e  lea     eax, [rdi+7FF40000h]
0x180038584  cmp     eax, 3FFh
0x180038589  ja      short loc_1800385A3
0x18003858b  mov     byte ptr [rsp+58h+lpBuffer], 0; bool
0x180038590  mov     r8, rbx; lpBuffer
0x180038593  mov     edx, edi; dwMessageId
0x180038595  lea     rcx, aUrlmonDll_0; "URLMON.DLL"
0x18003859c  call    ?SafeFormatMessage@Resources@@KAKPEBGKPEAGK_N@Z; Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)
0x1800385a1  mov     ecx, eax
0x1800385a3  nop
0x1800385a4  test    ecx, ecx
0x1800385a6  jz      short loc_1800385B8
0x1800385a8  xor     eax, eax
0x1800385aa  mov     [rbx+rcx*2], ax
0x1800385ae  mov     rcx, rbx; unsigned __int16 *
0x1800385b1  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800385b6  jmp     short loc_1800385DB
0x1800385b8  mov     ecx, edi; int
0x1800385ba  call    ?newString@String@@SAPEAV1@H@Z; String::newString(int)
0x1800385bf  mov     [rsp+58h+lpBuffer], 0; struct String *
0x1800385c8  xor     r9d, r9d; struct String *
0x1800385cb  xor     r8d, r8d; struct String *
0x1800385ce  mov     rdx, rax; struct String *
0x1800385d1  mov     ecx, 0C00CE30Ah; int
0x1800385d6  call    ?FormatMessageW@Resources@@SAPEAVString@@JPEAV2@000@Z; Resources::FormatMessageW(long,String *,String *,String *,String *)
0x1800385db  mov     [rsp+58h+var_18], rax
0x1800385e0  mov     rdi, rax
0x1800385e3  jmp     loc_18003868A
0x1800385e8  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800385ee  call    cs:__imp_TlsGetValue
0x1800385f4  mov     rbx, rax
0x1800385f7  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800385fe  jnz     short loc_180038679
0x180038600  call    cs:__imp__resetstkoflw
0x180038606  test    eax, eax
0x180038608  jnz     short loc_18003865B
0x18003860a  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180038611  test    rcx, rcx
0x180038614  jz      short loc_180038628
0x180038616  cmp     [rcx+50h], rbx
0x18003861a  jnz     short loc_180038628
0x18003861c  mov     rax, [rcx]
0x18003861f  mov     rax, [rax+20h]
0x180038623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038628  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18003862f  test    rcx, rcx
0x180038632  jz      short loc_180038646
0x180038634  cmp     [rcx+50h], rbx
0x180038638  jnz     short loc_180038646
0x18003863a  mov     rax, [rcx]
0x18003863d  mov     rax, [rax+20h]
0x180038641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038646  xor     r9d, r9d; lpArguments
0x180038649  xor     r8d, r8d; nNumberOfArguments
0x18003864c  xor     edx, edx; dwExceptionFlags
0x18003864e  mov     ecx, 0C00000FDh; dwExceptionCode
0x180038653  call    cs:__imp_RaiseException
0x180038659  jmp     short loc_180038679
0x18003865b  mov     rax, [rbx+60h]
0x18003865f  mov     [rbx+68h], rax
0x180038663  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18003866a  mov     [rbx+60h], rax
0x18003866e  mov     dword ptr [rbx+54h], 800703E9h
0x180038675  mov     byte ptr [rbx+78h], 0
0x180038679  lea     rdi, ?s_cstrEmpty@String@@2V_CodebaseString@@B; _CodebaseString const String::s_cstrEmpty
0x180038680  mov     [rsp+58h+var_18], rdi
0x180038685  mov     rbx, [rsp+58h+arg_8]
0x18003868a  mov     rcx, rbx; void *
0x18003868d  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x180038692  mov     rax, rdi
0x180038695  mov     rbx, [rsp+58h+arg_0]
0x18003869a  add     rsp, 50h
0x18003869e  pop     rdi
0x18003869f  retn
0x180103812  push    rbp
0x180103814  sub     rsp, 40h
0x180103818  mov     rbp, rdx
0x18010381b  xor     edx, edx; bool
0x18010381d  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180103822  nop
0x180103823  add     rsp, 40h
0x180103827  pop     rbp
0x180103828  retn
```
