# Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)

- ea: `0x18004a11c`
- end: `0x18004a142`
- name: `?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: ``
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023b84`
- `0x1800483f8`
- `0x18004858c`
- `0x180048860`
- `0x1800488a0`
- `0x18004892c`
- `0x18004897c`
- `0x1800492f0`
- `0x180049ba0`
- `0x18004a550`
- `0x18004a9f0`
- `0x18004bd00`
- `0x18004ca78`
- `0x18004d23c`
- `0x18004d798`
- `0x18004e4ec`
- `0x18004e6d8`
- `0x18004eb18`
- `0x18004ed7c`
- `0x18004ee8c`
- `0x18004f9d0`
- `0x180050350`
- `0x180050440`
- `0x180050550`
- `0x180050700`
- `0x180050aa0`
- `0x180051520`
- `0x1800519f4`
- `0x180052268`
- `0x1800529d0`
- `0x180052ae0`
- `0x180052d30`
- `0x180053ee0`
- `0x180054284`
- `0x180055688`
- `0x180055bec`
- `0x180056130`
- `0x1800587e4`
- `0x180058fc0`
- `0x18005af70`
- `0x18005d000`
- `0x180066b4c`
- `0x180066c80`
- `0x180066de4`
- `0x180066fcc`
- `0x180066fe4`
- `0x180067234`
- `0x1800672d0`
- `0x180067564`
- `0x18006b3c8`

## callees

- `0x18004a11c`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18004a11c  sub     rsp, 28h
0x18004a120  mov     rdx, rcx
0x18004a123  xor     eax, eax
0x18004a125  mov     rcx, [rcx]
0x18004a128  test    rcx, rcx
0x18004a12b  jz      short loc_18004A13D
0x18004a12d  mov     [rdx], rax
0x18004a130  mov     rax, [rcx]
0x18004a133  mov     rax, [rax+10h]
0x18004a137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a13c  nop
0x18004a13d  add     rsp, 28h
0x18004a141  retn
```
