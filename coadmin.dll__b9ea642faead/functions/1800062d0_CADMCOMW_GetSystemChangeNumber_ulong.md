# CADMCOMW::GetSystemChangeNumber(ulong *)

- ea: `0x1800062d0`
- end: `0x1800063b4`
- name: `?GetSystemChangeNumber@CADMCOMW@@UEAAJPEAK@Z`
- size: `228`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800062d0`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetSystemChangeNumber(CADMCOMW *this, unsigned int *a2)
{
  int v4; // ecx
  __int64 v5; // r8
  int v7; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v8; // [rsp+80h] [rbp+18h] BYREF

  v8 = 0;
  v7 = 0;
  if ( a2 )
  {
    v4 = CADMCOMW::LookupAndAccessCheck(this, 0, &v8, (__int64)&byte_1800127D8, 1u, 0, 0, 0, 0, 0, 0);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 4) + 320LL))(
             *((_QWORD *)this + 4),
             a2);
      if ( v4 >= 0 )
      {
        v5 = *((_QWORD *)this + 101);
        if ( v5 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v5 + 152LL))(*((_QWORD *)this + 101), &v7);
          if ( v4 >= 0 )
            *a2 += v7;
          else
            return 0;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800062d0  mov     rax, rsp
0x1800062d3  mov     [rax+8], rbx
0x1800062d7  push    rdi
0x1800062d8  sub     rsp, 60h
0x1800062dc  mov     dword ptr [rax+18h], 0
0x1800062e3  mov     rbx, rdx
0x1800062e6  mov     dword ptr [rax+10h], 0
0x1800062ed  mov     rdi, rcx
0x1800062f0  test    rdx, rdx
0x1800062f3  jnz     short loc_1800062FF
0x1800062f5  mov     ecx, 80070057h
0x1800062fa  jmp     loc_1800063A7
0x1800062ff  mov     [rsp+68h+var_18], 0
0x180006308  lea     r9, byte_1800127D8
0x18000630f  mov     [rsp+68h+var_20], 0
0x180006318  lea     r8, [rsp+68h+arg_10]
0x180006320  mov     [rsp+68h+var_28], 0
0x180006329  xor     edx, edx
0x18000632b  mov     [rsp+68h+var_30], 0
0x180006334  mov     [rsp+68h+var_38], 0
0x18000633d  mov     [rsp+68h+var_40], 0
0x180006345  mov     [rsp+68h+var_48], 1
0x18000634d  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180006352  mov     ecx, eax
0x180006354  test    eax, eax
0x180006356  js      short loc_1800063A7
0x180006358  mov     rcx, [rdi+20h]
0x18000635c  mov     rdx, rbx
0x18000635f  mov     rax, [rcx]
0x180006362  mov     rax, [rax+140h]
0x180006369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636e  mov     ecx, eax
0x180006370  test    eax, eax
0x180006372  js      short loc_1800063A7
0x180006374  mov     r8, [rdi+328h]
0x18000637b  test    r8, r8
0x18000637e  jz      short loc_1800063A7
0x180006380  mov     rax, [r8]
0x180006383  lea     rdx, [rsp+68h+arg_8]
0x180006388  mov     rcx, r8
0x18000638b  mov     rax, [rax+98h]
0x180006392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006397  mov     ecx, eax
0x180006399  test    eax, eax
0x18000639b  jns     short loc_1800063A1
0x18000639d  xor     ecx, ecx
0x18000639f  jmp     short loc_1800063A7
0x1800063a1  mov     eax, [rsp+68h+arg_8]
0x1800063a5  add     [rbx], eax
0x1800063a7  mov     rbx, [rsp+68h+arg_0]
0x1800063ac  mov     eax, ecx
0x1800063ae  add     rsp, 60h
0x1800063b2  pop     rdi
0x1800063b3  retn
```
