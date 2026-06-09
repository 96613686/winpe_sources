# CADMCOMW::ChangePermissions(ulong,ulong,ulong)

- ea: `0x180002f70`
- end: `0x180003041`
- name: `?ChangePermissions@CADMCOMW@@UEAAJKKK@Z`
- size: `209`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002f70`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::ChangePermissions(CADMCOMW *this, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 result; // rax
  unsigned int v8; // [rsp+78h] [rbp+10h] BYREF

  v8 = 0;
  if ( !a2 )
    return 2147942406LL;
  if ( (a4 & 3) == 0 || (a4 & 0xFFFFFFFC) != 0 )
    return 2147942487LL;
  result = CADMCOMW::LookupAndAccessCheck(
             this,
             a2,
             &v8,
             (__int64)&byte_1800127D8,
             4 * (a4 & 1),
             (a4 >> 1) & 1,
             0,
             0,
             0,
             0,
             0);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 296LL))(
             *((_QWORD *)this + 4),
             v8,
             a3,
             a4);
  return result;
}

```

## disassembly

```asm
0x180002f70  mov     [rsp+arg_0], rbx
0x180002f75  mov     [rsp+arg_10], rsi
0x180002f7a  push    rdi
0x180002f7b  sub     rsp, 60h
0x180002f7f  mov     [rsp+68h+arg_8], 0
0x180002f87  mov     ebx, r9d
0x180002f8a  mov     esi, r8d
0x180002f8d  mov     rdi, rcx
0x180002f90  test    edx, edx
0x180002f92  jnz     short loc_180002F9E
0x180002f94  mov     eax, 80070006h
0x180002f99  jmp     loc_18000302F
0x180002f9e  test    bl, 3
0x180002fa1  jz      loc_18000302A
0x180002fa7  test    ebx, 0FFFFFFFCh
0x180002fad  jnz     short loc_18000302A
0x180002faf  mov     [rsp+68h+var_18], 0
0x180002fb8  lea     r9, byte_1800127D8
0x180002fbf  mov     [rsp+68h+var_20], 0
0x180002fc8  lea     r8, [rsp+68h+arg_8]
0x180002fcd  mov     [rsp+68h+var_28], 0
0x180002fd6  mov     ecx, ebx
0x180002fd8  shr     ecx, 1
0x180002fda  mov     eax, ebx
0x180002fdc  and     ecx, 1
0x180002fdf  mov     [rsp+68h+var_30], 0
0x180002fe8  and     eax, 1
0x180002feb  mov     [rsp+68h+var_38], 0
0x180002ff4  mov     [rsp+68h+var_40], ecx
0x180002ff8  mov     rcx, rdi
0x180002ffb  shl     eax, 2
0x180002ffe  mov     [rsp+68h+var_48], eax
0x180003002  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180003007  test    eax, eax
0x180003009  js      short loc_18000302F
0x18000300b  mov     rcx, [rdi+20h]
0x18000300f  mov     r9d, ebx
0x180003012  mov     edx, [rsp+68h+arg_8]
0x180003016  mov     r8d, esi
0x180003019  mov     rax, [rcx]
0x18000301c  mov     rax, [rax+128h]
0x180003023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003028  jmp     short loc_18000302F
0x18000302a  mov     eax, 80070057h
0x18000302f  lea     r11, [rsp+68h+var_8]
0x180003034  mov     rbx, [r11+10h]
0x180003038  mov     rsi, [r11+20h]
0x18000303c  mov     rsp, r11
0x18000303f  pop     rdi
0x180003040  retn
```
