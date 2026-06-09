# ComputeService::Vmwp::Details::LookupWorkerProcessInterface(_GUID const &,IUnknown * *)

- ea: `0x18004eeb8`
- end: `0x18004f068`
- name: `?LookupWorkerProcessInterface@Details@Vmwp@ComputeService@@YA_NAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `432`
- prototype: `bool(ComputeService::Vmwp::Details *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004ed1c`

## callees

- `0x1800067c0`
- `0x18000995c`
- `0x180009e8c`
- `0x18001587c`
- `0x18004613c`
- `0x18004eeb8`
- `0x18004f184`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ef73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ef73`
- `combase!__imp_RoGetMachineGlobalObjectTable` at `0x18004ef89`
- `combase!__imp_RoGetMachineGlobalObjectTable` at `0x18004ef89`

## string_xrefs

- `0x18004f023`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x18004f056`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall ComputeService::Vmwp::Details::LookupWorkerProcessInterface(
        ComputeService::Vmwp::Details *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  int v3; // ebx
  _QWORD *v4; // rax
  unsigned int v5; // r8d
  unsigned __int64 v6; // rdx
  HRESULT StringReference; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int MachineGlobalObjectTable; // eax
  wil::details::in1diag3 *v11; // rcx
  int v12; // eax
  bool v13; // bl
  unsigned int v15; // eax
  int v16; // [rsp+20h] [rbp-69h]
  _QWORD v17[4]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v18; // [rsp+50h] [rbp-39h] BYREF
  __int128 hstringHeader; // [rsp+58h] [rbp-31h] BYREF
  __int128 hstringHeader_16; // [rsp+68h] [rbp-21h] BYREF
  WCHAR sourceString[8]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v22; // [rsp+90h] [rbp+7h]
  __int128 v23; // [rsp+A0h] [rbp+17h]
  __int128 v24; // [rsp+B0h] [rbp+27h]
  __int64 v25; // [rsp+C0h] [rbp+37h]
  __int16 v26; // [rsp+C8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = (int)a2;
  CommonUtilities::GuidToString(v17, this);
  v4 = v17;
  if ( v17[3] > 7u )
    v4 = (_QWORD *)v17[0];
  *(_OWORD *)sourceString = *(_OWORD *)v4;
  v22 = *((_OWORD *)v4 + 1);
  v23 = *((_OWORD *)v4 + 2);
  v24 = *((_OWORD *)v4 + 3);
  v25 = v4[8];
  std::wstring::~wstring(v17);
  v26 = 0;
  hstringHeader = 0;
  hstringHeader_16 = 0;
  v6 = -1;
  do
    ++v6;
  while ( sourceString[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, v5);
    __debugbreak();
  }
  if ( (int)v6 + 1 < (unsigned int)v6 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, v5);
    __debugbreak();
  }
  StringReference = WindowsCreateStringReference(
                      sourceString,
                      v6,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v8, v9);
LABEL_19:
    wil::details::in1diag3::Throw_Hr(
      v11,
      (void *)0x11E,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)(unsigned int)MachineGlobalObjectTable,
      v16);
  }
  v18 = 0;
  MachineGlobalObjectTable = RoGetMachineGlobalObjectTable(&v18);
  v11 = retaddr;
  if ( MachineGlobalObjectTable < 0 )
    goto LABEL_19;
  v12 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD, GUID *))(*(_QWORD *)v18 + 40LL))(
          v18,
          &CLSID_VmVirtualMachine,
          *((_QWORD *)&hstringHeader_16 + 1),
          &GUID_00000000_0000_0000_c000_000000000046);
  if ( v12 < 0 && v12 != -2147220997 && v12 != -2147221164 )
  {
    v15 = wil::verify_hresult<long>((unsigned int)v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)v15,
      v3);
  }
  v13 = v12 >= 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return v13;
}

```

## disassembly

```asm
0x18004eeb8  mov     [rsp-8+arg_10], rbx
0x18004eebd  mov     [rsp-8+arg_18], rdi
0x18004eec2  push    rbp
0x18004eec3  lea     rbp, [rsp-57h]
0x18004eec8  sub     rsp, 0E0h
0x18004eecf  mov     rax, cs:__security_cookie
0x18004eed6  xor     rax, rsp
0x18004eed9  mov     [rbp+57h+var_10], rax
0x18004eedd  mov     rbx, rdx
0x18004eee0  mov     rdx, rcx
0x18004eee3  lea     rcx, [rbp+57h+var_B0]
0x18004eee7  call    ?GuidToString@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; CommonUtilities::GuidToString(_GUID const &,bool)
0x18004eeec  lea     rax, [rbp+57h+var_B0]
0x18004eef0  cmp     [rbp+57h+var_98], 7
0x18004eef5  cmova   rax, [rbp+57h+var_B0]
0x18004eefa  movups  xmm0, xmmword ptr [rax]
0x18004eefd  movaps  xmmword ptr [rbp+57h+sourceString], xmm0
0x18004ef01  movups  xmm1, xmmword ptr [rax+10h]
0x18004ef05  movaps  [rbp+57h+var_50], xmm1
0x18004ef09  movups  xmm0, xmmword ptr [rax+20h]
0x18004ef0d  movaps  [rbp+57h+var_40], xmm0
0x18004ef11  movups  xmm1, xmmword ptr [rax+30h]
0x18004ef15  movaps  [rbp+57h+var_30], xmm1
0x18004ef19  movsd   xmm0, qword ptr [rax+40h]
0x18004ef1e  movsd   [rbp+57h+var_20], xmm0
0x18004ef23  lea     rcx, [rbp+57h+var_B0]
0x18004ef27  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ef2c  xor     edi, edi
0x18004ef2e  mov     [rbp+57h+var_18], di
0x18004ef32  xorps   xmm0, xmm0
0x18004ef35  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18004ef39  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved+10h], xmm0
0x18004ef3d  lea     rax, [rbp+57h+sourceString]
0x18004ef41  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004ef45  inc     rdx; int
0x18004ef48  cmp     [rax+rdx*2], di
0x18004ef4c  jnz     short loc_18004EF45
0x18004ef4e  mov     eax, 0FFFFFFFFh
0x18004ef53  cmp     rdx, rax
0x18004ef56  ja      loc_18004F035
0x18004ef5c  lea     eax, [rdx+1]
0x18004ef5f  cmp     eax, edx
0x18004ef61  jb      loc_18004F040
0x18004ef67  lea     r9, [rbp+57h+string]; string
0x18004ef6b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004ef6f  lea     rcx, [rbp+57h+sourceString]; sourceString
0x18004ef73  call    cs:__imp_WindowsCreateStringReference
0x18004ef79  test    eax, eax
0x18004ef7b  js      loc_18004F04B
0x18004ef81  mov     [rbp+57h+var_90], rdi
0x18004ef85  lea     rcx, [rbp+57h+var_90]
0x18004ef89  call    cs:__imp_RoGetMachineGlobalObjectTable
0x18004ef8f  mov     rcx, [rbp+5Fh]
0x18004ef93  test    eax, eax
0x18004ef95  js      loc_18004F053
0x18004ef9b  mov     rcx, [rbp+57h+var_90]
0x18004ef9f  mov     rax, [rcx]
0x18004efa2  mov     qword ptr [rsp+0E0h+var_C0], rbx; int
0x18004efa7  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x18004efae  mov     r8, [rbp+57h+string]
0x18004efb2  lea     rdx, CLSID_VmVirtualMachine
0x18004efb9  mov     rax, [rax+28h]
0x18004efbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efc2  mov     ebx, eax
0x18004efc4  test    eax, eax
0x18004efc6  jns     short loc_18004EFD6
0x18004efc8  cmp     eax, 800401FBh
0x18004efcd  jz      short loc_18004EFD6
0x18004efcf  cmp     eax, 80040154h
0x18004efd4  jnz     short loc_18004F015
0x18004efd6  shr     ebx, 1Fh
0x18004efd9  xor     bl, 1
0x18004efdc  mov     rcx, [rbp+57h+var_90]
0x18004efe0  test    rcx, rcx
0x18004efe3  jz      short loc_18004EFF2
0x18004efe5  mov     rax, [rcx]
0x18004efe8  mov     rax, [rax+10h]
0x18004efec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eff1  nop
0x18004eff2  mov     al, bl
0x18004eff4  mov     rcx, [rbp+57h+var_10]
0x18004eff8  xor     rcx, rsp; StackCookie
0x18004effb  call    __security_check_cookie
0x18004f000  lea     r11, [rsp+0E0h+var_s0]
0x18004f008  mov     rbx, [r11+20h]
0x18004f00c  mov     rdi, [r11+28h]
0x18004f010  mov     rsp, r11
0x18004f013  pop     rbp
0x18004f014  retn
0x18004f015  mov     ecx, ebx
0x18004f017  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004f01c  mov     r9d, eax; char *
0x18004f01f  mov     rcx, [rbp+5Fh]; this
0x18004f023  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x18004f02a  mov     edx, 12Bh; void *
0x18004f02f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f035  mov     ecx, 80070216h; this
0x18004f03a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004f03f  int     3; Trap to Debugger
0x18004f040  mov     ecx, 80070216h; this
0x18004f045  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004f04a  int     3; Trap to Debugger
0x18004f04b  mov     ecx, eax; this
0x18004f04d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004f052  nop
0x18004f053  mov     r9d, eax; char *
0x18004f056  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x18004f05d  mov     edx, 11Eh; void *
0x18004f062  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
