# CADMCOMW::GetDataSetNumber(ulong,ushort const *,ulong *)

- ea: `0x180005e90`
- end: `0x180005f69`
- name: `?GetDataSetNumber@CADMCOMW@@UEAAJKPEBGPEAK@Z`
- size: `217`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005e90`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetDataSetNumber(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  __int64 result; // rax
  __int64 v8; // rcx
  _DWORD v9[4]; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+98h] [rbp+20h] BYREF

  v10 = 0;
  v9[0] = 0;
  if ( !a4 )
    return 2147942487LL;
  result = CADMCOMW::LookupAndAccessCheck(this, a2, &v10, (__int64)a3, 1u, 0, 0, 0, 0, v9, 0);
  if ( (int)result >= 0 )
  {
    v8 = *((_QWORD *)this + 101);
    if ( v8 && v9[0] == 1 )
      return (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, unsigned int *))(*(_QWORD *)v8 + 160LL))(
               v8,
               v10,
               a3,
               a4);
    else
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 4)
                                                                                                 + 336LL))(
               *((_QWORD *)this + 4),
               v10,
               a3,
               a4);
  }
  return result;
}

```

## disassembly

```asm
0x180005e90  mov     rax, rsp
0x180005e93  mov     [rax+8], rbx
0x180005e97  mov     [rax+10h], rsi
0x180005e9b  push    rdi
0x180005e9c  sub     rsp, 70h
0x180005ea0  mov     dword ptr [rax+20h], 0
0x180005ea7  mov     rdi, r9
0x180005eaa  mov     dword ptr [rax-18h], 0
0x180005eb1  mov     rsi, r8
0x180005eb4  mov     rbx, rcx
0x180005eb7  test    r9, r9
0x180005eba  jnz     short loc_180005EC6
0x180005ebc  mov     eax, 80070057h
0x180005ec1  jmp     loc_180005F57
0x180005ec6  mov     [rsp+78h+var_28], 0
0x180005ecf  lea     rax, [rsp+78h+var_18]
0x180005ed4  mov     [rsp+78h+var_30], rax
0x180005ed9  lea     r8, [rsp+78h+arg_18]
0x180005ee1  mov     [rsp+78h+var_38], 0
0x180005eea  mov     r9, rsi
0x180005eed  mov     [rsp+78h+var_40], 0
0x180005ef6  mov     [rsp+78h+var_48], 0
0x180005eff  mov     [rsp+78h+var_50], 0
0x180005f07  mov     [rsp+78h+var_58], 1
0x180005f0f  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180005f14  test    eax, eax
0x180005f16  js      short loc_180005F57
0x180005f18  mov     rcx, [rbx+328h]
0x180005f1f  test    rcx, rcx
0x180005f22  jz      short loc_180005F37
0x180005f24  cmp     [rsp+78h+var_18], 1
0x180005f29  jnz     short loc_180005F37
0x180005f2b  mov     rax, [rcx]
0x180005f2e  mov     rax, [rax+0A0h]
0x180005f35  jmp     short loc_180005F45
0x180005f37  mov     rcx, [rbx+20h]
0x180005f3b  mov     rax, [rcx]
0x180005f3e  mov     rax, [rax+150h]
0x180005f45  mov     edx, [rsp+78h+arg_18]
0x180005f4c  mov     r9, rdi
0x180005f4f  mov     r8, rsi
0x180005f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f57  lea     r11, [rsp+78h+var_8]
0x180005f5c  mov     rbx, [r11+10h]
0x180005f60  mov     rsi, [r11+18h]
0x180005f64  mov     rsp, r11
0x180005f67  pop     rdi
0x180005f68  retn
```
