# CJob::EditWorkItem(HWND__ *,ulong)

- ea: `0x18000b710`
- end: `0x18000b730`
- name: `?EditWorkItem@CJob@@UEAAJPEAUHWND__@@K@Z`
- size: `32`
- prototype: `__int64 __fastcall(struct ITask *this, HWND, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000b710`
- `0x18000ff30`

## pseudocode

```c
__int64 __fastcall CJob::EditWorkItem(struct ITask *this, HWND a2)
{
  struct ITaskVtbl *lpVtbl; // rcx

  lpVtbl = this[19].lpVtbl;
  if ( lpVtbl && LOWORD(lpVtbl->QueryInterface) )
    return I_DisplayJobProperties((LPCWSTR)lpVtbl, this);
  else
    return 2147680519LL;
}

```

## disassembly

```asm
0x18000b710  mov     rdx, rcx; struct ITask *
0x18000b713  xor     eax, eax
0x18000b715  mov     rcx, [rcx+98h]; pszPath
0x18000b71c  test    rcx, rcx
0x18000b71f  jz      short loc_18000B72A
0x18000b721  cmp     [rcx], ax
0x18000b724  jnz     ?I_DisplayJobProperties@@YAJPEAGPEAUITask@@@Z; I_DisplayJobProperties(ushort *,ITask *)
0x18000b72a  mov     eax, 80030107h
0x18000b72f  retn
```
