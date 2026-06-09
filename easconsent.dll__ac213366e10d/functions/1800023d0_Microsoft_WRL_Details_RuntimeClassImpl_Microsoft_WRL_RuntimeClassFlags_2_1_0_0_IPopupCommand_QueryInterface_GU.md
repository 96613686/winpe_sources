# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800023d0`
- end: `0x180002444`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommand@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800023d0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  int v4; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != 1146277385
      || a2[1] != *(_DWORD *)&GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data2
      || a2[2] != *(_DWORD *)GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] != v4 )
    return (unsigned int)-2147467262;
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x1800023d0  push    rbx
0x1800023d2  sub     rsp, 20h
0x1800023d6  xor     ebx, ebx
0x1800023d8  mov     [r8], rbx
0x1800023db  cmp     [rdx], ebx
0x1800023dd  jnz     short loc_180002411
0x1800023df  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1800023e5  cmp     [rdx+4], eax
0x1800023e8  jnz     short loc_180002437
0x1800023ea  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800023f0  cmp     [rdx+8], eax
0x1800023f3  jnz     short loc_180002437
0x1800023f5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800023fb  cmp     [rdx+0Ch], eax
0x1800023fe  jnz     short loc_180002437
0x180002400  mov     [r8], rcx
0x180002403  mov     rax, [rcx]
0x180002406  mov     rax, [rax+8]
0x18000240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240f  jmp     short loc_18000243C
0x180002411  cmp     dword ptr [rdx], 4452CE09h
0x180002417  jnz     short loc_180002437
0x180002419  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data2
0x18000241f  cmp     [rdx+4], eax
0x180002422  jnz     short loc_180002437
0x180002424  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4
0x18000242a  cmp     [rdx+8], eax
0x18000242d  jnz     short loc_180002437
0x18000242f  mov     eax, dword ptr cs:_GUID_4452ce09_0488_4ca7_a896_c4f140907549.Data4+4
0x180002435  jmp     short loc_1800023FB
0x180002437  mov     ebx, 80004002h
0x18000243c  mov     eax, ebx
0x18000243e  add     rsp, 20h
0x180002442  pop     rbx
0x180002443  retn
```
