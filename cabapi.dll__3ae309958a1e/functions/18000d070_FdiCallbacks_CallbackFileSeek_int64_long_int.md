# FdiCallbacks::CallbackFileSeek(__int64,long,int)

- ea: `0x18000d070`
- end: `0x18000d0a5`
- name: `?CallbackFileSeek@FdiCallbacks@@SAJ_JJH@Z`
- size: `53`
- prototype: `DWORD __fastcall(HANDLE *hf, LONG dist, int seektype)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000d070`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000d09e`

## pseudocode

```c
DWORD __fastcall FdiCallbacks::CallbackFileSeek(HANDLE *hf, LONG dist, int seektype)
{
  int v3; // r8d
  DWORD v5; // r9d

  if ( seektype )
  {
    v3 = seektype - 1;
    if ( v3 )
    {
      if ( v3 != 1 )
        return -1;
      v5 = 2;
    }
    else
    {
      v5 = 1;
    }
  }
  else
  {
    v5 = 0;
  }
  return SetFilePointer(*hf, dist, 0, v5);
}

```

## disassembly

```asm
0x18000d070  test    r8d, r8d
0x18000d073  jz      short loc_18000D095
0x18000d075  sub     r8d, 1
0x18000d079  jz      short loc_18000D08D
0x18000d07b  cmp     r8d, 1
0x18000d07f  jz      short loc_18000D085
0x18000d081  or      eax, 0FFFFFFFFh
0x18000d084  retn
0x18000d085  mov     r9d, 2
0x18000d08b  jmp     short loc_18000D098
0x18000d08d  mov     r9d, 1
0x18000d093  jmp     short loc_18000D098
0x18000d095  xor     r9d, r9d
0x18000d098  mov     rcx, [rcx]
0x18000d09b  xor     r8d, r8d
0x18000d09e  jmp     cs:__imp_SetFilePointer
```
