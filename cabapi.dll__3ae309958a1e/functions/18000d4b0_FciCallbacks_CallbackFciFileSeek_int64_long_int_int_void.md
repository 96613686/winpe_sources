# FciCallbacks::CallbackFciFileSeek(__int64,long,int,int *,void *)

- ea: `0x18000d4b0`
- end: `0x18000d50b`
- name: `?CallbackFciFileSeek@FciCallbacks@@SAJ_JJHPEAHPEAX@Z`
- size: `91`
- prototype: `__int64 __fastcall(INT_PTR hf, LONG dist, int seektype, DWORD *err)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000d4b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4f6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000d4e9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000d4e9`

## pseudocode

```c
__int64 __fastcall FciCallbacks::CallbackFciFileSeek(INT_PTR hf, LONG dist, int seektype, DWORD *err)
{
  int v5; // r8d
  DWORD v6; // ebx
  DWORD v7; // r9d

  if ( seektype )
  {
    v5 = seektype - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
      {
        v6 = -1;
LABEL_9:
        *err = GetLastError();
        return v6;
      }
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
  }
  v6 = SetFilePointer((HANDLE)hf, dist, 0, v7);
  if ( v6 == -1 )
    goto LABEL_9;
  return v6;
}

```

## disassembly

```asm
0x18000d4b0  mov     [rsp+arg_0], rbx
0x18000d4b5  push    rdi
0x18000d4b6  sub     rsp, 20h
0x18000d4ba  mov     rdi, r9
0x18000d4bd  test    r8d, r8d
0x18000d4c0  jz      short loc_18000D4E3
0x18000d4c2  sub     r8d, 1
0x18000d4c6  jz      short loc_18000D4DB
0x18000d4c8  cmp     r8d, 1
0x18000d4cc  jz      short loc_18000D4D3
0x18000d4ce  or      ebx, 0FFFFFFFFh
0x18000d4d1  jmp     short loc_18000D4F6
0x18000d4d3  mov     r9d, 2
0x18000d4d9  jmp     short loc_18000D4E6
0x18000d4db  mov     r9d, 1
0x18000d4e1  jmp     short loc_18000D4E6
0x18000d4e3  xor     r9d, r9d; dwMoveMethod
0x18000d4e6  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000d4e9  call    cs:__imp_SetFilePointer
0x18000d4ef  mov     ebx, eax
0x18000d4f1  cmp     eax, 0FFFFFFFFh
0x18000d4f4  jnz     short loc_18000D4FE
0x18000d4f6  call    cs:__imp_GetLastError
0x18000d4fc  mov     [rdi], eax
0x18000d4fe  mov     eax, ebx
0x18000d500  mov     rbx, [rsp+28h+arg_0]
0x18000d505  add     rsp, 20h
0x18000d509  pop     rdi
0x18000d50a  retn
```
