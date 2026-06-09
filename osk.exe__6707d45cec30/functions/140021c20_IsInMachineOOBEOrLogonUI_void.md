# IsInMachineOOBEOrLogonUI(void)

- ea: `0x140021c20`
- end: `0x140021c5d`
- name: `?IsInMachineOOBEOrLogonUI@@YA_NXZ`
- size: `61`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140021e5c`
- `0x140021f84`

## callees

- `0x140021c20`
- `0x140021c64`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140021c4f`
- `KERNEL32!CloseHandle` at `0x140021c4f`
- `KERNEL32!OpenMutexW` at `0x140021c3f`
- `KERNEL32!OpenMutexW` at `0x140021c3f`

## pseudocode

```c
char IsInMachineOOBEOrLogonUI(void)
{
  char v0; // bl
  HANDLE v1; // rax

  v0 = IsLogonUI();
  if ( !v0 )
  {
    v1 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    if ( v1 )
    {
      v0 = 1;
      CloseHandle(v1);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140021c20  push    rbx
0x140021c22  sub     rsp, 20h
0x140021c26  call    ?IsLogonUI@@YA_NXZ; IsLogonUI(void)
0x140021c2b  mov     bl, al
0x140021c2d  test    al, al
0x140021c2f  jnz     short loc_140021C55
0x140021c31  lea     r8, aGlobalWindowsM; "Global\\Windows.Machine.OOBE"
0x140021c38  xor     edx, edx; bInheritHandle
0x140021c3a  mov     ecx, 100000h; dwDesiredAccess
0x140021c3f  call    cs:__imp_OpenMutexW
0x140021c45  test    rax, rax
0x140021c48  jz      short loc_140021C55
0x140021c4a  mov     rcx, rax; hObject
0x140021c4d  mov     bl, 1
0x140021c4f  call    cs:__imp_CloseHandle
0x140021c55  mov     al, bl
0x140021c57  add     rsp, 20h
0x140021c5b  pop     rbx
0x140021c5c  retn
```
