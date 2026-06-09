# Microsoft::WRL::Details::RuntimeClassBaseT<6>::AsIID<Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>>(Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0> *,_GUID const &,void * *)

- ea: `0x180001d40`
- end: `0x180001dfd`
- name: `??$AsIID@V?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@WRL@Microsoft@@@?$RuntimeClassBaseT@$05@Details@WRL@Microsoft@@KAJPEAV?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@23@AEBU_GUID@@PEAPEAX@Z`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001e50`
- `0x180003fe0`

## callees

- `0x180001d40`
- `0x180001fa0`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<6>::AsIID<Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v3; // r9
  __int64 v4; // r9
  unsigned int v6; // ebx

  v3 = a1;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == 1
      && a2[1] == *(_DWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data2
      && a2[2] == *(_DWORD *)GUID_00000001_0000_0000_c000_000000000046.Data4
      && a2[3] == *(_DWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data4[4] )
    {
      goto LABEL_12;
    }
  }
  else if ( a2[1] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
         && a2[2] == *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
         && a2[3] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000001_0000_0000_c000_000000000046, a3, a1) )
    return (unsigned int)-2147467262;
  v3 = v4 + 8;
LABEL_12:
  v6 = 0;
  *a3 = v3;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  return v6;
}

```

## disassembly

```asm
0x180001d40  push    rbx
0x180001d42  sub     rsp, 20h
0x180001d46  mov     r9, rcx
0x180001d49  mov     qword ptr [r8], 0
0x180001d50  mov     ecx, [rdx]
0x180001d52  mov     rax, rdx
0x180001d55  test    ecx, ecx
0x180001d57  jz      short loc_180001D7B
0x180001d59  cmp     ecx, 1
0x180001d5c  jz      short loc_180001DB6
0x180001d5e  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x180001d65  mov     rcx, rax
0x180001d68  call    InlineIsEqualGUID
0x180001d6d  test    eax, eax
0x180001d6f  jz      loc_180001DF6
0x180001d75  add     r9, 8
0x180001d79  jmp     short loc_180001DD7
0x180001d7b  mov     ecx, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180001d81  cmp     [rdx+4], ecx
0x180001d84  jnz     short loc_180001D5E
0x180001d86  mov     ecx, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180001d8c  cmp     [rdx+8], ecx
0x180001d8f  jnz     short loc_180001D5E
0x180001d91  mov     ecx, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180001d97  cmp     [rdx+0Ch], ecx
0x180001d9a  jnz     short loc_180001D5E
0x180001d9c  mov     [r8], r9
0x180001d9f  mov     rcx, r9
0x180001da2  mov     rax, [r9]
0x180001da5  mov     rax, [rax+8]
0x180001da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dae  xor     eax, eax
0x180001db0  add     rsp, 20h
0x180001db4  pop     rbx
0x180001db5  retn
0x180001db6  mov     ecx, dword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data2
0x180001dbc  cmp     [rdx+4], ecx
0x180001dbf  jnz     short loc_180001D5E
0x180001dc1  mov     ecx, dword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x180001dc7  cmp     [rdx+8], ecx
0x180001dca  jnz     short loc_180001D5E
0x180001dcc  mov     ecx, dword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4+4
0x180001dd2  cmp     [rdx+0Ch], ecx
0x180001dd5  jnz     short loc_180001D5E
0x180001dd7  mov     rax, r9
0x180001dda  xor     ebx, ebx
0x180001ddc  mov     [r8], rax
0x180001ddf  mov     rcx, r9
0x180001de2  mov     rax, [r9]
0x180001de5  mov     rax, [rax+8]
0x180001de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dee  mov     eax, ebx
0x180001df0  add     rsp, 20h
0x180001df4  pop     rbx
0x180001df5  retn
0x180001df6  mov     ebx, 80004002h
0x180001dfb  jmp     short loc_180001DEE
```
