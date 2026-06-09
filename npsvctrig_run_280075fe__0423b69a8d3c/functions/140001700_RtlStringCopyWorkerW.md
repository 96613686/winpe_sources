# RtlStringCopyWorkerW

- ea: `0x140001700`
- end: `0x140001755`
- name: `RtlStringCopyWorkerW`
- size: `85`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140009410`

## callees

- `0x140001700`

## string_xrefs

- `0x140001703`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\NetworkServiceTriggers\Triggers\`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCopyWorkerW(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  wchar_t *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rax
  NTSTATUS v9; // r8d
  NTSTATUS result; // eax

  v6 = L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\NetworkServiceTriggers\\Triggers\\";
  v7 = 2147483646;
  v8 = 257;
  v9 = 0;
  while ( v7 && *v6 )
  {
    *pszDest++ = *v6++;
    --v7;
    if ( !--v8 )
    {
      --pszDest;
      v9 = -2147483643;
      break;
    }
  }
  result = v9;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x140001700  mov     rdx, rcx
0x140001703  lea     r9, RTDS_TRIGGER_KEY; "\\Registry\\Machine\\Software\\Microsof"...
0x14000170a  mov     ecx, 7FFFFFFEh
0x14000170f  mov     eax, 101h
0x140001714  xor     r8d, r8d
0x140001717  test    rcx, rcx
0x14000171a  jz      short loc_14000174C
0x14000171c  movzx   r10d, word ptr [r9]
0x140001720  test    r10w, r10w
0x140001724  jz      short loc_14000173D
0x140001726  mov     [rdx], r10w
0x14000172a  add     r9, 2
0x14000172e  add     rdx, 2
0x140001732  dec     rcx
0x140001735  sub     rax, 1
0x140001739  jnz     short loc_140001717
0x14000173b  jmp     short loc_140001742
0x14000173d  test    rax, rax
0x140001740  jnz     short loc_14000174C
0x140001742  sub     rdx, 2
0x140001746  mov     r8d, 80000005h
0x14000174c  xor     ecx, ecx
0x14000174e  mov     eax, r8d
0x140001751  mov     [rdx], cx
0x140001754  retn
```
