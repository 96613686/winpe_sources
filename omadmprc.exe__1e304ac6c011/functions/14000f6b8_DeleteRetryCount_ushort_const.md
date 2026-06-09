# DeleteRetryCount(ushort const *)

- ea: `0x14000f6b8`
- end: `0x14000f763`
- name: `?DeleteRetryCount@@YAJPEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000fff0`
- `0x140012060`
- `0x14001401c`

## callees

- `0x14000f6b8`

## import_xrefs

- `DMCmnUtils!BigStrcat` at `0x14000f6f4`
- `DMCmnUtils!BigStrcat` at `0x14000f6f4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000f6c5`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000f6c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f749`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f749`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14000f720`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14000f720`

## pseudocode

```c
__int64 __fastcall DeleteRetryCount(const unsigned __int16 *a1)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v3; // rdx
  const WCHAR *v4; // rax
  WCHAR *v5; // rdi
  unsigned int v6; // ebx
  LSTATUS v7; // eax

  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v3 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v3 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v4 = BigStrcat(3u, v3, L"\\", a1);
  v5 = (WCHAR *)v4;
  if ( v4 )
  {
    v7 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v4, L"RetryCount");
    v6 = 0;
    if ( v7 != 2 && v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      else
        v6 = v7;
    }
  }
  else
  {
    v6 = -2147024882;
  }
  LocalFree(v5);
  return v6;
}

```

## disassembly

```asm
0x14000f6b8  mov     [rsp+arg_0], rbx
0x14000f6bd  push    rdi
0x14000f6be  sub     rsp, 20h
0x14000f6c2  mov     rbx, rcx
0x14000f6c5  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000f6cc  nop     dword ptr [rax+rax+00h]
0x14000f6d1  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x14000f6d8  mov     r9, rbx
0x14000f6db  test    al, al
0x14000f6dd  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x14000f6e4  lea     r8, asc_140019FC8; "\\"
0x14000f6eb  cmovz   rdx, rcx
0x14000f6ef  mov     ecx, 3
0x14000f6f4  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x14000f6fb  nop     dword ptr [rax+rax+00h]
0x14000f700  mov     rdi, rax
0x14000f703  test    rax, rax
0x14000f706  jnz     short loc_14000F70F
0x14000f708  mov     ebx, 8007000Eh
0x14000f70d  jmp     short loc_14000F746
0x14000f70f  lea     r8, ValueName; "RetryCount"
0x14000f716  mov     rdx, rdi; lpSubKey
0x14000f719  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000f720  call    cs:__imp_RegDeleteKeyValueW
0x14000f727  nop     dword ptr [rax+rax+00h]
0x14000f72c  xor     ebx, ebx
0x14000f72e  cmp     eax, 2
0x14000f731  jz      short loc_14000F746
0x14000f733  test    eax, eax
0x14000f735  jz      short loc_14000F746
0x14000f737  jg      short loc_14000F73D
0x14000f739  mov     ebx, eax
0x14000f73b  jmp     short loc_14000F746
0x14000f73d  movzx   ebx, ax
0x14000f740  or      ebx, 80070000h
0x14000f746  mov     rcx, rdi; hMem
0x14000f749  call    cs:__imp_LocalFree
0x14000f750  nop     dword ptr [rax+rax+00h]
0x14000f755  mov     eax, ebx
0x14000f757  mov     rbx, [rsp+28h+arg_0]
0x14000f75c  add     rsp, 20h
0x14000f760  pop     rdi
0x14000f761  retn
```
