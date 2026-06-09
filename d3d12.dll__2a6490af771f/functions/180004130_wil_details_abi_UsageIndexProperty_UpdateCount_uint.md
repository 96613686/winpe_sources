# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180004130`
- end: `0x18000418c`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `92`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800039ac`
- `0x180003d88`
- `0x18000dd50`

## callees

- `0x180004130`
- `0x18000463c`
- `0x18000be22`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000415e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000415e`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexProperty::UpdateCount(wil::details_abi::UsageIndexProperty *this, int a2)
{
  _DWORD *v2; // r8
  char v3; // al
  _WORD *v4; // rdx

  v2 = (_DWORD *)((char *)this + 4);
  if ( *((_DWORD *)this + 1) != a2 )
  {
    v3 = *((_BYTE *)this + 2);
    *v2 = a2;
    if ( v3 == 1 )
    {
      v4 = (_WORD *)*((_QWORD *)this + 2);
      if ( v4 )
      {
        *v4 = *(_WORD *)v2;
      }
      else
      {
        *(_DWORD *)_o__errno() = 22;
        invalid_parameter_noinfo();
      }
    }
    else if ( v3 == 2 )
    {
      memcpy_s(*((void *const *)this + 2), 4u, v2, 4u);
    }
  }
}

```

## disassembly

```asm
0x180004130  sub     rsp, 28h
0x180004134  lea     r8, [rcx+4]
0x180004138  cmp     [r8], edx
0x18000413b  jnz     short loc_180004142
0x18000413d  add     rsp, 28h
0x180004141  retn
0x180004142  mov     al, [rcx+2]
0x180004145  mov     [r8], edx
0x180004148  cmp     al, 1
0x18000414a  jnz     short loc_180004173
0x18000414c  mov     rdx, [rcx+10h]
0x180004150  test    rdx, rdx
0x180004153  jz      short loc_18000415E
0x180004155  movzx   eax, word ptr [r8]
0x180004159  mov     [rdx], ax
0x18000415c  jmp     short loc_18000413D
0x18000415e  call    cs:__imp__o__errno
0x180004164  mov     dword ptr [rax], 16h
0x18000416a  add     rsp, 28h
0x18000416e  jmp     _invalid_parameter_noinfo
0x180004173  cmp     al, 2
0x180004175  jnz     short loc_18000413D
0x180004177  mov     rcx, [rcx+10h]
0x18000417b  mov     edx, 4
0x180004180  mov     r9d, edx
0x180004183  add     rsp, 28h
0x180004187  jmp     memcpy_s
```
