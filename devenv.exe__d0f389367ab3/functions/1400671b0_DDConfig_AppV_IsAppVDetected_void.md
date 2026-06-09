# DDConfig::AppV::IsAppVDetected(void)

- ea: `0x1400671b0`
- end: `0x1400672d0`
- name: `?IsAppVDetected@AppV@DDConfig@@SA_NXZ`
- size: `288`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x140066a90`
- `0x140066e70`
- `0x140067060`

## callees

- `0x140002c10`
- `0x140002f00`
- `0x140007740`
- `0x140033ab0`
- `0x1400671b0`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x140067216`
- `KERNEL32!OpenEventW` at `0x140067216`
- `KERNEL32!CreateFileW` at `0x140067258`
- `KERNEL32!CreateFileW` at `0x140067258`
- `KERNEL32!GetCurrentProcessId` at `0x1400671ed`
- `KERNEL32!GetCurrentProcessId` at `0x1400671ed`
- `KERNEL32!CloseHandle` at `0x14006728a`
- `KERNEL32!CloseHandle` at `0x14006728a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool DDConfig::AppV::IsAppVDetected(void)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  DWORD CurrentProcessId; // eax
  LPCWSTR v2; // rbx
  HANDLE FileW; // rsi
  const wchar_t *v4; // rdx
  LPCWSTR lpName; // [rsp+50h] [rbp+8h] BYREF

  if ( DDConfig::AppV::isInitialized )
    return DDConfig::AppV::isAppV;
  lpName = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  lpName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  CurrentProcessId = GetCurrentProcessId();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpName,
    L"AppVVirtual-%d",
    CurrentProcessId);
  v2 = lpName;
  FileW = OpenEventW(0x80000000, 0, lpName);
  if ( FileW )
  {
    v4 = L"5.0";
  }
  else
  {
    FileW = CreateFileW(L"\\\\.\\GLOBAL\\VE-UM", 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_8;
    v4 = L"4.6";
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&DDConfig::AppV::strAppVVersion, v4);
  DDConfig::AppV::isAppV = 1;
  CloseHandle(FileW);
LABEL_8:
  DDConfig::AppV::isInitialized = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 - 3) + 8LL))(*((_QWORD *)v2 - 3));
  }
  return DDConfig::AppV::isAppV;
}

```

## disassembly

```asm
0x1400671b0  mov     [rsp+arg_8], rbx
0x1400671b5  push    rsi
0x1400671b6  sub     rsp, 40h
0x1400671ba  cmp     cs:?isInitialized@AppV@DDConfig@@0_NA, 0; bool DDConfig::AppV::isInitialized
0x1400671c1  jnz     loc_1400672B4
0x1400671c7  and     [rsp+48h+lpName], 0
0x1400671cd  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400671d2  mov     rcx, rax
0x1400671d5  test    rax, rax
0x1400671d8  jz      loc_1400672C5
0x1400671de  mov     rax, [rax]
0x1400671e1  call    qword ptr [rax+18h]
0x1400671e4  add     rax, 18h
0x1400671e8  mov     [rsp+48h+lpName], rax
0x1400671ed  call    cs:__imp_GetCurrentProcessId
0x1400671f3  mov     r8d, eax
0x1400671f6  lea     rdx, aAppvvirtualD; "AppVVirtual-%d"
0x1400671fd  lea     rcx, [rsp+48h+lpName]
0x140067202  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140067207  mov     rbx, [rsp+48h+lpName]
0x14006720c  mov     r8, rbx; lpName
0x14006720f  xor     edx, edx; bInheritHandle
0x140067211  mov     ecx, 80000000h; dwDesiredAccess
0x140067216  call    cs:__imp_OpenEventW
0x14006721c  mov     rsi, rax
0x14006721f  mov     r8d, 3; dwShareMode
0x140067225  test    rax, rax
0x140067228  jz      short loc_140067233
0x14006722a  lea     rdx, a50; "5.0"
0x140067231  jmp     short loc_140067274
0x140067233  and     [rsp+48h+var_18], 0
0x140067239  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140067241  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140067249  xor     r9d, r9d; lpSecurityAttributes
0x14006724c  mov     edx, 0C0000000h; dwDesiredAccess
0x140067251  lea     rcx, aGlobalVeUm; "\\\\.\\GLOBAL\\VE-UM"
0x140067258  call    cs:__imp_CreateFileW
0x14006725e  mov     rsi, rax
0x140067261  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140067265  jz      short loc_140067290
0x140067267  mov     r8d, 3
0x14006726d  lea     rdx, a46; "4.6"
0x140067274  lea     rcx, ?strAppVVersion@AppV@DDConfig@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> DDConfig::AppV::strAppVVersion
0x14006727b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140067280  mov     cs:?isAppV@AppV@DDConfig@@0_NA, 1; bool DDConfig::AppV::isAppV
0x140067287  mov     rcx, rsi; hObject
0x14006728a  call    cs:__imp_CloseHandle
0x140067290  mov     cs:?isInitialized@AppV@DDConfig@@0_NA, 1; bool DDConfig::AppV::isInitialized
0x140067297  lea     rdx, [rbx-18h]
0x14006729b  or      eax, 0FFFFFFFFh
0x14006729e  lock xadd [rdx+10h], eax
0x1400672a3  sub     eax, 1
0x1400672a6  jg      short loc_1400672B4
0x1400672a8  lfence
0x1400672ab  mov     rcx, [rdx]
0x1400672ae  mov     rax, [rcx]
0x1400672b1  call    qword ptr [rax+8]
0x1400672b4  mov     al, cs:?isAppV@AppV@DDConfig@@0_NA; bool DDConfig::AppV::isAppV
0x1400672ba  mov     rbx, [rsp+48h+arg_8]
0x1400672bf  add     rsp, 40h
0x1400672c3  pop     rsi
0x1400672c4  retn
0x1400672c5  mov     ecx, 80004005h; int
0x1400672ca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
