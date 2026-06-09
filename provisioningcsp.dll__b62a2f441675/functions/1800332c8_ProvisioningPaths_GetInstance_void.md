# ProvisioningPaths::GetInstance(void)

- ea: `0x1800332c8`
- end: `0x18003332b`
- name: `?GetInstance@ProvisioningPaths@@CAAEAV1@XZ`
- size: `99`
- prototype: `struct ProvisioningPaths *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180033334`

## callees

- `0x180002a38`
- `0x1800032e0`
- `0x180003350`
- `0x1800332c8`

## pseudocode

```c
struct ProvisioningPaths *ProvisioningPaths::GetInstance(void)
{
  if ( dword_18004A400 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18004A400);
    if ( dword_18004A400 == -1 )
    {
      atexit(ProvisioningPaths::GetInstance_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_18004A400);
    }
  }
  return (struct ProvisioningPaths *)qword_18004A408;
}

```

## disassembly

```asm
0x1800332c8  sub     rsp, 28h
0x1800332cc  mov     ecx, cs:_tls_index
0x1800332d2  mov     rax, gs:58h
0x1800332db  mov     edx, 4
0x1800332e0  mov     rax, [rax+rcx*8]
0x1800332e4  mov     eax, [rdx+rax]
0x1800332e7  cmp     cs:dword_18004A400, eax
0x1800332ed  jg      short loc_1800332FC
0x1800332ef  lea     rax, qword_18004A408
0x1800332f6  add     rsp, 28h
0x1800332fa  retn
0x1800332fc  lea     rcx, dword_18004A400
0x180033303  call    _Init_thread_header
0x180033308  cmp     cs:dword_18004A400, 0FFFFFFFFh
0x18003330f  jnz     short loc_1800332EF
0x180033311  lea     rcx, _ProvisioningPaths__GetInstance____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x180033318  call    atexit
0x18003331d  lea     rcx, dword_18004A400
0x180033324  call    _Init_thread_footer
0x180033329  jmp     short loc_1800332EF
```
