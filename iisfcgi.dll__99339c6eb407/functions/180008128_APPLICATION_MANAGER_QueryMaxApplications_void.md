# APPLICATION_MANAGER::QueryMaxApplications(void)

- ea: `0x180008128`
- end: `0x18000815c`
- name: `?QueryMaxApplications@APPLICATION_MANAGER@@QEAAKXZ`
- size: `52`
- prototype: `unsigned int __fastcall(APPLICATION_MANAGER *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005068`
- `0x180007180`
- `0x18000794c`
- `0x1800083d0`

## callees

- `0x180008128`

## pseudocode

```c
__int64 __fastcall APPLICATION_MANAGER::QueryMaxApplications(APPLICATION_MANAGER *this)
{
  __int64 result; // rax
  unsigned int v2; // r8d

  result = *((unsigned int *)this + 121);
  if ( !(_DWORD)result )
  {
    v2 = APPLICATION_MANAGER::sm_dwSuggestedMaxChangeNumber;
    if ( *((_DWORD *)this + 123) != APPLICATION_MANAGER::sm_dwSuggestedMaxChangeNumber )
    {
      *((_DWORD *)this + 122) = APPLICATION_MANAGER::sm_dwSuggestedMaxApplications;
      *((_DWORD *)this + 123) = v2;
    }
    return *((unsigned int *)this + 122);
  }
  return result;
}

```

## disassembly

```asm
0x180008128  mov     eax, [rcx+1E4h]
0x18000812e  test    eax, eax
0x180008130  jnz     short locret_18000815B
0x180008132  mov     r8d, cs:?sm_dwSuggestedMaxChangeNumber@APPLICATION_MANAGER@@0KA; ulong APPLICATION_MANAGER::sm_dwSuggestedMaxChangeNumber
0x180008139  cmp     [rcx+1ECh], r8d
0x180008140  jz      short loc_180008155
0x180008142  mov     eax, cs:?sm_dwSuggestedMaxApplications@APPLICATION_MANAGER@@0KA; ulong APPLICATION_MANAGER::sm_dwSuggestedMaxApplications
0x180008148  mov     [rcx+1E8h], eax
0x18000814e  mov     [rcx+1ECh], r8d
0x180008155  mov     eax, [rcx+1E8h]
0x18000815b  retn
```
