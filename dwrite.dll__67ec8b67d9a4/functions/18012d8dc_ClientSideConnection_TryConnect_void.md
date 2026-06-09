# ClientSideConnection::TryConnect(void)

- ea: `0x18012d8dc`
- end: `0x18012da28`
- name: `?TryConnect@ClientSideConnection@@AEAAJXZ`
- size: `332`
- prototype: `__int64 __fastcall(ClientSideConnection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18012cf64`

## callees

- `0x18012cf34`
- `0x18012d8dc`
- `0x18012da30`
- `0x1801efaac`
- `0x180212490`
- `0x180212f4c`

## import_xrefs

- `ntdll!NtClose` at `0x18012da20`
- `ntdll!NtClose` at `0x18012da20`
- `ntdll!RtlInitUnicodeString` at `0x18012d928`
- `ntdll!RtlInitUnicodeString` at `0x18012d928`
- `ntdll!NtAlpcConnectPort` at `0x18012d9bd`
- `ntdll!NtAlpcConnectPort` at `0x18012d9bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012d904`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012d904`

## string_xrefs

- `0x18012d90a`: `\BaseNamedObjects\FontCachePort`

## pseudocode

```c
__int64 __fastcall ClientSideConnection::TryConnect(ClientSideConnection *this)
{
  DWORD v2; // edx
  unsigned int v3; // eax
  int v4; // edi
  void *v5; // rcx
  __int64 v7; // [rsp+60h] [rbp-49h] BYREF
  __int64 v8; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v9[3]; // [rsp+70h] [rbp-39h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-21h] BYREF
  _DWORD v11[3]; // [rsp+A0h] [rbp-9h] BYREF
  __int16 v12; // [rsp+ACh] [rbp+3h]
  __int64 v13; // [rsp+B0h] [rbp+7h]
  int v14; // [rsp+E0h] [rbp+37h]

  v7 = 0;
  *((_DWORD *)this + 19) = GetTickCount();
  v8 = -10000000;
  RtlInitUnicodeString(&DestinationString, L"\\BaseNamedObjects\\FontCachePort");
  Sid::Sid((Sid *)v9, v2);
  memset_0(v11, 0, 0x48u);
  v11[0] = 720896;
  v14 = 4093;
  v11[1] = 12;
  v11[2] = 2;
  v12 = 257;
  v13 = 0x7FFF;
  v3 = NtAlpcConnectPort(&v7, &DestinationString, 0, v11, 0x20000, v9[0], 0, 0, 0, 0, &v8);
  v4 = StatusToHResult(v3);
  if ( v4 >= 0 )
  {
    v5 = (void *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = v7;
    if ( v5 )
      NtClose(v5);
    *((_DWORD *)this + 20) = 1000;
  }
  if ( v9[0] )
    std::_Deallocate<16>(v9[0], v9[2] - v9[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18012d8dc  mov     [rsp-8+arg_8], rbx
0x18012d8e1  mov     [rsp-8+arg_10], rdi
0x18012d8e6  push    rbp
0x18012d8e7  lea     rbp, [rsp-57h]
0x18012d8ec  sub     rsp, 100h
0x18012d8f3  mov     rax, cs:__security_cookie
0x18012d8fa  xor     rax, rsp
0x18012d8fd  mov     [rbp+57h+var_10], rax
0x18012d901  mov     rbx, rcx
0x18012d904  call    cs:__imp_GetTickCount
0x18012d90a  lea     rdx, ?FontCacheServerAlpcPortName@@3QB_WB; "\\BaseNamedObjects\\FontCachePort"
0x18012d911  mov     [rbp+57h+var_A0], 0
0x18012d919  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18012d91d  mov     [rbx+4Ch], eax
0x18012d920  mov     [rbp+57h+var_98], 0FFFFFFFFFF676980h
0x18012d928  call    cs:__imp_RtlInitUnicodeString
0x18012d92e  lea     rcx, [rbp+57h+var_90]; this
0x18012d932  call    ??0Sid@@QEAA@W4WELL_KNOWN_SID_TYPE@@@Z; Sid::Sid(WELL_KNOWN_SID_TYPE)
0x18012d937  xor     edx, edx; Val
0x18012d939  lea     rcx, [rbp+57h+var_60]; void *
0x18012d93d  lea     r8d, [rdx+48h]; Size
0x18012d941  call    memset_0
0x18012d946  mov     rax, [rbp+57h+var_90]
0x18012d94a  lea     rcx, [rbp+57h+var_98]
0x18012d94e  mov     [rsp+100h+var_B0], rcx
0x18012d953  lea     r9, [rbp+57h+var_60]
0x18012d957  mov     [rsp+100h+var_B8], 0
0x18012d960  lea     rdx, [rbp+57h+DestinationString]
0x18012d964  mov     [rsp+100h+var_C0], 0
0x18012d96d  lea     rcx, [rbp+57h+var_A0]
0x18012d971  mov     [rsp+100h+var_C8], 0
0x18012d97a  xor     r8d, r8d
0x18012d97d  mov     [rsp+100h+var_D0], 0
0x18012d986  mov     [rsp+100h+var_D8], rax
0x18012d98b  mov     [rsp+100h+var_E0], 20000h
0x18012d993  mov     [rbp+57h+var_60], 0B0000h
0x18012d99a  mov     [rbp+57h+var_20], 0FFDh
0x18012d9a1  mov     [rbp+57h+var_5C], 0Ch
0x18012d9a8  mov     [rbp+57h+var_58], 2
0x18012d9af  mov     [rbp+57h+var_54], 101h
0x18012d9b5  mov     [rbp+57h+var_50], 7FFFh
0x18012d9bd  call    cs:__imp_NtAlpcConnectPort
0x18012d9c3  mov     ecx, eax; unsigned int
0x18012d9c5  call    ?StatusToHResult@@YAJJ@Z; StatusToHResult(long)
0x18012d9ca  mov     edi, eax
0x18012d9cc  test    eax, eax
0x18012d9ce  js      short loc_18012D9E8
0x18012d9d0  mov     rcx, [rbx+30h]; Handle
0x18012d9d4  mov     rdx, [rbp+57h+var_A0]
0x18012d9d8  mov     [rbx+30h], rdx
0x18012d9dc  test    rcx, rcx
0x18012d9df  jnz     short loc_18012DA20
0x18012d9e1  mov     dword ptr [rbx+50h], 3E8h
0x18012d9e8  mov     rcx, [rbp+57h+var_90]
0x18012d9ec  test    rcx, rcx
0x18012d9ef  jz      short loc_18012D9FD
0x18012d9f1  mov     rdx, [rbp+57h+var_80]
0x18012d9f5  sub     rdx, rcx
0x18012d9f8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012d9fd  mov     eax, edi
0x18012d9ff  mov     rcx, [rbp+57h+var_10]
0x18012da03  xor     rcx, rsp; StackCookie
0x18012da06  call    __security_check_cookie
0x18012da0b  lea     r11, [rsp+100h+var_s0]
0x18012da13  mov     rbx, [r11+18h]
0x18012da17  mov     rdi, [r11+20h]
0x18012da1b  mov     rsp, r11
0x18012da1e  pop     rbp
0x18012da1f  retn
0x18012da20  call    cs:__imp_NtClose
0x18012da26  jmp     short loc_18012D9E1
```
