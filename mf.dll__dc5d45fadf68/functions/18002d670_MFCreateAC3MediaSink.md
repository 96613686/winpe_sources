# MFCreateAC3MediaSink

- ea: `0x18002d670`
- end: `0x18002d864`
- name: `MFCreateAC3MediaSink`
- size: `500`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000f370`
- `0x1800104b0`
- `0x180010600`
- `0x180018064`
- `0x180018e70`
- `0x18002d670`
- `0x180034b38`
- `0x180065ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d6c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d6c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d6e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d7a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d6e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d7a2`

## string_xrefs

- `0x18002d692`: `MFCreateAC3MediaSink_Stub`
- `0x18002d740`: `MFCreateAC3MediaSink_Stub`
- `0x18002d800`: `MFCreateAC3MediaSink_Stub`

## pseudocode

```c
__int64 __fastcall MFCreateAC3MediaSink(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT Instance; // ebx
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  LPVOID ppv[7]; // [rsp+30h] [rbp-38h] BYREF
  char v16; // [rsp+88h] [rbp+20h] BYREF

  ppv[0] = 0;
  sub_18000F370(&v16, "MFCreateAC3MediaSink_Stub", 267);
  Instance = CoCreateInstance(&stru_18006F218, 0, 1u, &stru_1800701F8, ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64, __int64))(*(_QWORD *)ppv[0] + 24LL))(
                 ppv[0],
                 a1,
                 0,
                 a2,
                 a3);
    if ( Instance < 0 )
    {
      v11 = (__int64 *)qword_180084A30;
      if ( !qword_180084A30 )
      {
        v12 = MFGetCallStackTracingWeakReference();
        qword_180084A30 = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)qword_180084A30;
        }
        else
        {
          v11 = &qword_180083DB0;
          qword_180084A30 = (__int64)&qword_180083DB0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = sub_180010600();
        if ( *(_DWORD *)(v13 + 1996) != Instance )
          sub_180034B38(v13, "MFCreateAC3MediaSink_Stub", 268, (unsigned int)Instance);
      }
      if ( byte_180084958 )
      {
        v10 = 19;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v7 = (__int64 *)qword_180084A30;
    if ( !qword_180084A30 )
    {
      v8 = MFGetCallStackTracingWeakReference();
      qword_180084A30 = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)qword_180084A30;
      }
      else
      {
        v7 = &qword_180083DB0;
        qword_180084A30 = (__int64)&qword_180083DB0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = sub_180010600();
      if ( *(_DWORD *)(v9 + 1996) != Instance )
        sub_180034B38(v9, "MFCreateAC3MediaSink_Stub", 267, (unsigned int)Instance);
    }
    if ( byte_180084958 )
    {
      v10 = 18;
LABEL_23:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v10, qword_180070010, 0, Instance);
    }
  }
  sub_1800104B0(&v16);
  sub_180018064(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002d670  mov     rax, rsp
0x18002d673  push    rbx
0x18002d674  push    rbp
0x18002d675  push    rsi
0x18002d676  push    rdi
0x18002d677  sub     rsp, 48h
0x18002d67b  mov     rdi, r8
0x18002d67e  mov     qword ptr [rax-38h], 0
0x18002d686  mov     rsi, rdx
0x18002d689  mov     rbp, rcx
0x18002d68c  mov     r8d, 10Bh
0x18002d692  lea     rdx, aMfcreateac3med_0; "MFCreateAC3MediaSink_Stub"
0x18002d699  lea     rcx, [rax+20h]
0x18002d69d  call    sub_18000F370
0x18002d6a2  xor     edx, edx; pUnkOuter
0x18002d6a4  lea     rax, [rsp+68h+var_38]
0x18002d6a9  lea     r9, stru_1800701F8; riid
0x18002d6b0  mov     [rsp+68h+ppv], rax; ppv
0x18002d6b5  lea     rcx, stru_18006F218; rclsid
0x18002d6bc  lea     r8d, [rdx+1]; dwClsContext
0x18002d6c0  call    cs:CoCreateInstance
0x18002d6c7  nop     dword ptr [rax+rax+00h]
0x18002d6cc  mov     ebx, eax
0x18002d6ce  test    eax, eax
0x18002d6d0  jns     loc_18002D76C
0x18002d6d6  mov     rcx, cs:qword_180084A30
0x18002d6dd  test    rcx, rcx
0x18002d6e0  jnz     short loc_18002D72A
0x18002d6e2  call    cs:MFGetCallStackTracingWeakReference
0x18002d6e9  nop     dword ptr [rax+rax+00h]
0x18002d6ee  mov     cs:qword_180084A30, rax
0x18002d6f5  mov     rcx, rax
0x18002d6f8  test    rax, rax
0x18002d6fb  jz      short loc_18002D71C
0x18002d6fd  mov     rax, [rax]
0x18002d700  mov     edx, 7F0h
0x18002d705  mov     rax, [rax+8]
0x18002d709  call    cs:__guard_dispatch_icall_fptr
0x18002d70f  test    eax, eax
0x18002d711  jz      short loc_18002D71C
0x18002d713  mov     rcx, cs:qword_180084A30
0x18002d71a  jmp     short loc_18002D72A
0x18002d71c  lea     rcx, qword_180083DB0
0x18002d723  mov     cs:qword_180084A30, rcx
0x18002d72a  cmp     byte ptr [rcx+8], 0
0x18002d72e  jz      short loc_18002D755
0x18002d730  call    sub_180010600
0x18002d735  cmp     [rax+7CCh], ebx
0x18002d73b  jz      short loc_18002D755
0x18002d73d  mov     r9d, ebx
0x18002d740  lea     rdx, aMfcreateac3med_0; "MFCreateAC3MediaSink_Stub"
0x18002d747  mov     r8d, 10Bh
0x18002d74d  mov     rcx, rax
0x18002d750  call    sub_180034B38
0x18002d755  cmp     cs:byte_180084958, 1
0x18002d75c  jb      loc_18002D841
0x18002d762  mov     edx, 12h
0x18002d767  jmp     loc_18002D823
0x18002d76c  mov     rcx, [rsp+68h+var_38]
0x18002d771  mov     r9, rsi
0x18002d774  xor     r8d, r8d
0x18002d777  mov     [rsp+68h+ppv], rdi
0x18002d77c  mov     rdx, rbp
0x18002d77f  mov     rax, [rcx]
0x18002d782  mov     rax, [rax+18h]
0x18002d786  call    cs:__guard_dispatch_icall_fptr
0x18002d78c  mov     ebx, eax
0x18002d78e  test    eax, eax
0x18002d790  jns     loc_18002D841
0x18002d796  mov     rcx, cs:qword_180084A30
0x18002d79d  test    rcx, rcx
0x18002d7a0  jnz     short loc_18002D7EA
0x18002d7a2  call    cs:MFGetCallStackTracingWeakReference
0x18002d7a9  nop     dword ptr [rax+rax+00h]
0x18002d7ae  mov     cs:qword_180084A30, rax
0x18002d7b5  mov     rcx, rax
0x18002d7b8  test    rax, rax
0x18002d7bb  jz      short loc_18002D7DC
0x18002d7bd  mov     rax, [rax]
0x18002d7c0  mov     edx, 7F0h
0x18002d7c5  mov     rax, [rax+8]
0x18002d7c9  call    cs:__guard_dispatch_icall_fptr
0x18002d7cf  test    eax, eax
0x18002d7d1  jz      short loc_18002D7DC
0x18002d7d3  mov     rcx, cs:qword_180084A30
0x18002d7da  jmp     short loc_18002D7EA
0x18002d7dc  lea     rcx, qword_180083DB0
0x18002d7e3  mov     cs:qword_180084A30, rcx
0x18002d7ea  cmp     byte ptr [rcx+8], 0
0x18002d7ee  jz      short loc_18002D815
0x18002d7f0  call    sub_180010600
0x18002d7f5  cmp     [rax+7CCh], ebx
0x18002d7fb  jz      short loc_18002D815
0x18002d7fd  mov     r9d, ebx
0x18002d800  lea     rdx, aMfcreateac3med_0; "MFCreateAC3MediaSink_Stub"
0x18002d807  mov     r8d, 10Ch
0x18002d80d  mov     rcx, rax
0x18002d810  call    sub_180034B38
0x18002d815  cmp     cs:byte_180084958, 1
0x18002d81c  jb      short loc_18002D841
0x18002d81e  mov     edx, 13h
0x18002d823  mov     rcx, cs:RequestContext
0x18002d82a  lea     r8, qword_180070010
0x18002d831  xor     r9d, r9d
0x18002d834  mov     dword ptr [rsp+68h+ppv], ebx
0x18002d838  mov     rcx, [rcx+10h]
0x18002d83c  call    sub_180018E70
0x18002d841  lea     rcx, [rsp+68h+arg_18]
0x18002d849  call    sub_1800104B0
0x18002d84e  lea     rcx, [rsp+68h+var_38]
0x18002d853  call    sub_180018064
0x18002d858  mov     eax, ebx
0x18002d85a  add     rsp, 48h
0x18002d85e  pop     rdi
0x18002d85f  pop     rsi
0x18002d860  pop     rbp
0x18002d861  pop     rbx
0x18002d862  retn
```
