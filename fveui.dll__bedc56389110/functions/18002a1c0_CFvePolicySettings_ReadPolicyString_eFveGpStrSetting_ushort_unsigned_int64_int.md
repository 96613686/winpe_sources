# CFvePolicySettings::ReadPolicyString(eFveGpStrSetting,ushort * *,unsigned __int64 *,int *)

- ea: `0x18002a1c0`
- end: `0x18002a228`
- name: `?ReadPolicyString@CFvePolicySettings@@IEBAJW4eFveGpStrSetting@@PEAPEAGPEA_KPEAH@Z`
- size: `104`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002a500`

## callees

- `0x180029ea8`
- `0x18002a1c0`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall CFvePolicySettings::ReadPolicyString(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, int *a5)
{
  __int64 result; // rax
  int v9; // ecx

  result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
  if ( (_DWORD)result == -2147024894 )
  {
    result = CFvePolicySettings::GetDefaultPolicyString(a2, a3, a4);
    if ( (int)result < 0 )
      return result;
    v9 = 0;
  }
  else
  {
    v9 = 1;
    if ( (int)result < 0 )
      return result;
  }
  if ( a5 )
    *a5 = v9;
  return result;
}

```

## disassembly

```asm
0x18002a1c0  mov     [rsp+arg_0], rbx
0x18002a1c5  mov     [rsp+arg_8], rsi
0x18002a1ca  push    rdi
0x18002a1cb  sub     rsp, 30h
0x18002a1cf  mov     rcx, [rcx+8]
0x18002a1d3  mov     rbx, r9
0x18002a1d6  mov     rdi, r8
0x18002a1d9  mov     esi, edx
0x18002a1db  mov     rax, [rcx]
0x18002a1de  mov     rax, [rax+8]
0x18002a1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1e7  cmp     eax, 80070002h
0x18002a1ec  jnz     short loc_18002A203
0x18002a1ee  mov     r8, rbx
0x18002a1f1  mov     rdx, rdi
0x18002a1f4  mov     ecx, esi
0x18002a1f6  call    ?GetDefaultPolicyString@CFvePolicySettings@@KAJW4eFveGpStrSetting@@PEAPEAGPEA_K@Z; CFvePolicySettings::GetDefaultPolicyString(eFveGpStrSetting,ushort * *,unsigned __int64 *)
0x18002a1fb  test    eax, eax
0x18002a1fd  js      short loc_18002A218
0x18002a1ff  xor     ecx, ecx
0x18002a201  jmp     short loc_18002A20C
0x18002a203  mov     ecx, 1
0x18002a208  test    eax, eax
0x18002a20a  js      short loc_18002A218
0x18002a20c  mov     rdx, [rsp+38h+arg_20]
0x18002a211  test    rdx, rdx
0x18002a214  jz      short loc_18002A218
0x18002a216  mov     [rdx], ecx
0x18002a218  mov     rbx, [rsp+38h+arg_0]
0x18002a21d  mov     rsi, [rsp+38h+arg_8]
0x18002a222  add     rsp, 30h
0x18002a226  pop     rdi
0x18002a227  retn
```
