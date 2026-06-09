# FwhcGetFilterDetails

- ea: `0x18000bf3c`
- end: `0x18000c14d`
- name: `FwhcGetFilterDetails`
- size: `529`
- prototype: `__int64 __usercall@<rax>(UINT64 id@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009978`

## callees

- `0x18000ba00`
- `0x18000bcc4`
- `0x18000bf3c`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18000c136`
- `fwpuclnt!FwpmEngineClose0` at `0x18000c136`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c118`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c122`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c12c`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c118`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c122`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c12c`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000bfae`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000bfae`
- `fwpuclnt!FwpmFilterGetById0` at `0x18000bfd9`
- `fwpuclnt!FwpmFilterGetById0` at `0x18000bfd9`
- `fwpuclnt!FwpmProviderGetByKey0` at `0x18000c023`
- `fwpuclnt!FwpmProviderGetByKey0` at `0x18000c023`
- `fwpuclnt!FwpmProviderContextGetByKey3` at `0x18000c09d`
- `fwpuclnt!FwpmProviderContextGetByKey3` at `0x18000c09d`

## pseudocode

```c
__int64 __fastcall FwhcGetFilterDetails(UINT64 id, _QWORD *a2, _QWORD *a3, _QWORD *a4, _QWORD *a5)
{
  signed int v9; // eax
  signed int v10; // ebx
  signed int v11; // eax
  GUID *providerKey; // rdx
  signed int v13; // eax
  wchar_t *description; // rcx
  int v15; // eax
  __int64 v16; // rcx
  FWPM_FILTER0 *filter; // [rsp+30h] [rbp-40h] BYREF
  HANDLE engineHandle; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  __int64 v21; // [rsp+48h] [rbp-28h] BYREF
  __int64 v22; // [rsp+50h] [rbp-20h] BYREF
  FWPM_PROVIDER0 *provider; // [rsp+58h] [rbp-18h] BYREF
  __int64 v24; // [rsp+60h] [rbp-10h] BYREF
  void *p; // [rsp+68h] [rbp-8h] BYREF

  engineHandle = 0;
  filter = 0;
  provider = 0;
  p = 0;
  v22 = 0;
  v21 = 0;
  v24 = 0;
  v20 = 0;
  v9 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, &engineHandle);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_25;
  v11 = FwpmFilterGetById0(engineHandle, id, &filter);
  v10 = v11;
  if ( v11 > 0 )
    v10 = (unsigned __int16)v11 | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_25;
  v10 = FwhcCopyString(filter->displayData.name, &v24);
  if ( v10 < 0 )
    goto LABEL_25;
  providerKey = filter->providerKey;
  if ( providerKey )
  {
    v13 = FwpmProviderGetByKey0(engineHandle, providerKey, &provider);
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_25;
    v10 = FwhcCopyString(provider->displayData.name, &v22);
    if ( v10 < 0 )
      goto LABEL_25;
    description = provider->displayData.description;
  }
  else
  {
    v10 = FwhcCopyString(0, &v22);
    if ( v10 < 0 )
      goto LABEL_25;
    description = 0;
  }
  v10 = FwhcCopyString(description, &v21);
  if ( v10 < 0 )
    goto LABEL_25;
  if ( (filter->flags & 4) != 0 )
  {
    v15 = FwpmProviderContextGetByKey3(engineHandle, &filter->rawContext, &p);
    v10 = v15;
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_25;
    v16 = *((_QWORD *)p + 2);
  }
  else
  {
    v16 = 0;
  }
  v10 = FwhcCopyString(v16, &v20);
  if ( v10 < 0 )
  {
LABEL_25:
    FwhcFreeMem(&v20);
    FwhcFreeMem(&v24);
    FwhcFreeMem(&v21);
    FwhcFreeMem(&v22);
    goto LABEL_26;
  }
  *a2 = v22;
  *a3 = v21;
  *a4 = v24;
  *a5 = v20;
LABEL_26:
  FwpmFreeMemory0(&p);
  FwpmFreeMemory0((void **)&provider);
  FwpmFreeMemory0((void **)&filter);
  FwpmEngineClose0(engineHandle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000bf3c  push    rbp
0x18000bf3e  push    rbx
0x18000bf3f  push    rsi
0x18000bf40  push    rdi
0x18000bf41  push    r13
0x18000bf43  push    r14
0x18000bf45  push    r15
0x18000bf47  mov     rbp, rsp
0x18000bf4a  sub     rsp, 70h
0x18000bf4e  mov     rsi, r9
0x18000bf51  mov     [rbp+var_38], 0
0x18000bf59  mov     r14, r8
0x18000bf5c  mov     [rbp+filter], 0
0x18000bf64  mov     r15, rdx
0x18000bf67  mov     [rbp+provider], 0
0x18000bf6f  mov     rdi, rcx
0x18000bf72  mov     [rbp+p], 0
0x18000bf7a  lea     rax, [rbp+var_38]
0x18000bf7e  mov     [rbp+var_20], 0
0x18000bf86  xor     r9d, r9d; session
0x18000bf89  mov     [rsp+70h+engineHandle], rax; engineHandle
0x18000bf8e  xor     r8d, r8d; authIdentity
0x18000bf91  mov     [rbp+var_28], 0
0x18000bf99  or      edx, 0FFFFFFFFh; authnService
0x18000bf9c  mov     [rbp+var_10], 0
0x18000bfa4  xor     ecx, ecx; serverName
0x18000bfa6  mov     [rbp+var_30], 0
0x18000bfae  call    cs:__imp_FwpmEngineOpen0
0x18000bfb4  mov     ebx, eax
0x18000bfb6  mov     r13d, 80070000h
0x18000bfbc  test    eax, eax
0x18000bfbe  jle     short loc_18000BFC6
0x18000bfc0  movzx   ebx, ax
0x18000bfc3  or      ebx, r13d
0x18000bfc6  test    ebx, ebx
0x18000bfc8  js      loc_18000C0F0
0x18000bfce  mov     rcx, [rbp+var_38]; engineHandle
0x18000bfd2  lea     r8, [rbp+filter]; filter
0x18000bfd6  mov     rdx, rdi; id
0x18000bfd9  call    cs:__imp_FwpmFilterGetById0
0x18000bfdf  mov     ebx, eax
0x18000bfe1  test    eax, eax
0x18000bfe3  jle     short loc_18000BFEB
0x18000bfe5  movzx   ebx, ax
0x18000bfe8  or      ebx, r13d
0x18000bfeb  test    ebx, ebx
0x18000bfed  js      loc_18000C0F0
0x18000bff3  mov     rcx, [rbp+filter]
0x18000bff7  lea     rdx, [rbp+var_10]
0x18000bffb  mov     rcx, [rcx+10h]
0x18000bfff  call    FwhcCopyString
0x18000c004  mov     ebx, eax
0x18000c006  test    eax, eax
0x18000c008  js      loc_18000C0F0
0x18000c00e  mov     rax, [rbp+filter]
0x18000c012  mov     rdx, [rax+28h]; key
0x18000c016  test    rdx, rdx
0x18000c019  jz      short loc_18000C062
0x18000c01b  mov     rcx, [rbp+var_38]; engineHandle
0x18000c01f  lea     r8, [rbp+provider]; provider
0x18000c023  call    cs:__imp_FwpmProviderGetByKey0
0x18000c029  mov     ebx, eax
0x18000c02b  test    eax, eax
0x18000c02d  jle     short loc_18000C035
0x18000c02f  movzx   ebx, ax
0x18000c032  or      ebx, r13d
0x18000c035  test    ebx, ebx
0x18000c037  js      loc_18000C0F0
0x18000c03d  mov     rcx, [rbp+provider]
0x18000c041  lea     rdx, [rbp+var_20]
0x18000c045  mov     rcx, [rcx+10h]
0x18000c049  call    FwhcCopyString
0x18000c04e  mov     ebx, eax
0x18000c050  test    eax, eax
0x18000c052  js      loc_18000C0F0
0x18000c058  mov     rcx, [rbp+provider]
0x18000c05c  mov     rcx, [rcx+18h]
0x18000c060  jmp     short loc_18000C075
0x18000c062  lea     rdx, [rbp+var_20]
0x18000c066  xor     ecx, ecx
0x18000c068  call    FwhcCopyString
0x18000c06d  mov     ebx, eax
0x18000c06f  test    eax, eax
0x18000c071  js      short loc_18000C0F0
0x18000c073  xor     ecx, ecx
0x18000c075  lea     rdx, [rbp+var_28]
0x18000c079  call    FwhcCopyString
0x18000c07e  mov     ebx, eax
0x18000c080  test    eax, eax
0x18000c082  js      short loc_18000C0F0
0x18000c084  mov     rdx, [rbp+filter]
0x18000c088  test    byte ptr [rdx+20h], 4
0x18000c08c  jz      short loc_18000C0BD
0x18000c08e  mov     rcx, [rbp+var_38]
0x18000c092  lea     r8, [rbp+p]
0x18000c096  add     rdx, 98h
0x18000c09d  call    cs:__imp_FwpmProviderContextGetByKey3
0x18000c0a3  mov     ebx, eax
0x18000c0a5  test    eax, eax
0x18000c0a7  jle     short loc_18000C0AF
0x18000c0a9  movzx   ebx, ax
0x18000c0ac  or      ebx, r13d
0x18000c0af  test    ebx, ebx
0x18000c0b1  js      short loc_18000C0F0
0x18000c0b3  mov     rcx, [rbp+p]
0x18000c0b7  mov     rcx, [rcx+10h]
0x18000c0bb  jmp     short loc_18000C0BF
0x18000c0bd  xor     ecx, ecx
0x18000c0bf  lea     rdx, [rbp+var_30]
0x18000c0c3  call    FwhcCopyString
0x18000c0c8  mov     ebx, eax
0x18000c0ca  test    eax, eax
0x18000c0cc  js      short loc_18000C0F0
0x18000c0ce  mov     rax, [rbp+var_20]
0x18000c0d2  mov     rcx, [rbp+arg_20]
0x18000c0d6  mov     [r15], rax
0x18000c0d9  mov     rax, [rbp+var_28]
0x18000c0dd  mov     [r14], rax
0x18000c0e0  mov     rax, [rbp+var_10]
0x18000c0e4  mov     [rsi], rax
0x18000c0e7  mov     rax, [rbp+var_30]
0x18000c0eb  mov     [rcx], rax
0x18000c0ee  jmp     short loc_18000C114
0x18000c0f0  lea     rcx, [rbp+var_30]
0x18000c0f4  call    FwhcFreeMem
0x18000c0f9  lea     rcx, [rbp+var_10]
0x18000c0fd  call    FwhcFreeMem
0x18000c102  lea     rcx, [rbp+var_28]
0x18000c106  call    FwhcFreeMem
0x18000c10b  lea     rcx, [rbp+var_20]
0x18000c10f  call    FwhcFreeMem
0x18000c114  lea     rcx, [rbp+p]; p
0x18000c118  call    cs:__imp_FwpmFreeMemory0
0x18000c11e  lea     rcx, [rbp+provider]; p
0x18000c122  call    cs:__imp_FwpmFreeMemory0
0x18000c128  lea     rcx, [rbp+filter]; p
0x18000c12c  call    cs:__imp_FwpmFreeMemory0
0x18000c132  mov     rcx, [rbp+var_38]; engineHandle
0x18000c136  call    cs:__imp_FwpmEngineClose0
0x18000c13c  mov     eax, ebx
0x18000c13e  add     rsp, 70h
0x18000c142  pop     r15
0x18000c144  pop     r14
0x18000c146  pop     r13
0x18000c148  pop     rdi
0x18000c149  pop     rsi
0x18000c14a  pop     rbx
0x18000c14b  pop     rbp
0x18000c14c  retn
```
