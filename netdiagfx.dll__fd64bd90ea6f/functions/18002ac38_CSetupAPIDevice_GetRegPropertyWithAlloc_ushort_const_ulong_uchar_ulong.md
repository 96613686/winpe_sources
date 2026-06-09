# CSetupAPIDevice::GetRegPropertyWithAlloc(ushort const *,ulong *,uchar * *,ulong *)

- ea: `0x18002ac38`
- end: `0x18002acdd`
- name: `?GetRegPropertyWithAlloc@CSetupAPIDevice@@QEAAJPEBGPEAKPEAPEAE1@Z`
- size: `165`
- prototype: `__int64 __fastcall(CSetupAPIDevice *this, const unsigned __int16 *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002a920`

## callees

- `0x18002ab88`
- `0x18002ac38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ac79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ac79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002acc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002acc4`

## pseudocode

```c
__int64 __fastcall CSetupAPIDevice::GetRegPropertyWithAlloc(
        CSetupAPIDevice *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  const unsigned __int16 *v8; // rdx
  unsigned __int8 *v9; // rdi
  int RegProperty; // ebx
  unsigned int *v11; // rdx
  unsigned int v12; // ecx
  unsigned int cb[14]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+10h] BYREF
  int v16; // [rsp+7Ch] [rbp+14h]

  v16 = HIDWORD(a2);
  v15 = 0;
  cb[0] = 0;
  CSetupAPIDevice::GetRegProperty(this, a2, &v15, 0, cb);
  v9 = (unsigned __int8 *)CoTaskMemAlloc(cb[0]);
  if ( v9 )
  {
    RegProperty = CSetupAPIDevice::GetRegProperty(this, v8, &v15, v9, cb);
    if ( RegProperty < 0 )
    {
      CoTaskMemFree(v9);
    }
    else
    {
      v11 = a5;
      *a3 = v15;
      v12 = cb[0];
      *a4 = v9;
      *v11 = v12;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)RegProperty;
}

```

## disassembly

```asm
0x18002ac38  mov     rax, rsp
0x18002ac3b  mov     [rax+10h], rdx
0x18002ac3f  push    rbx
0x18002ac40  push    rsi
0x18002ac41  push    rdi
0x18002ac42  push    r14
0x18002ac44  sub     rsp, 48h
0x18002ac48  mov     dword ptr [rax+10h], 0
0x18002ac4f  mov     rsi, r9
0x18002ac52  mov     dword ptr [rax-38h], 0
0x18002ac59  lea     rax, [rax-38h]
0x18002ac5d  mov     r14, r8
0x18002ac60  mov     [rsp+68h+var_48], rax; unsigned int *
0x18002ac65  xor     r9d, r9d; unsigned __int8 *
0x18002ac68  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18002ac6d  mov     rbx, rcx
0x18002ac70  call    ?GetRegProperty@CSetupAPIDevice@@QEAAJPEBGPEAKPEAE1@Z; CSetupAPIDevice::GetRegProperty(ushort const *,ulong *,uchar *,ulong *)
0x18002ac75  mov     ecx, [rsp+68h+cb]; cb
0x18002ac79  call    cs:__imp_CoTaskMemAlloc
0x18002ac7f  mov     rdi, rax
0x18002ac82  test    rax, rax
0x18002ac85  jz      short loc_18002ACCC
0x18002ac87  lea     rax, [rsp+68h+cb]
0x18002ac8c  mov     r9, rdi; unsigned __int8 *
0x18002ac8f  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18002ac94  mov     [rsp+68h+var_48], rax; unsigned int *
0x18002ac99  mov     rcx, rbx; this
0x18002ac9c  call    ?GetRegProperty@CSetupAPIDevice@@QEAAJPEBGPEAKPEAE1@Z; CSetupAPIDevice::GetRegProperty(ushort const *,ulong *,uchar *,ulong *)
0x18002aca1  mov     ebx, eax
0x18002aca3  test    eax, eax
0x18002aca5  js      short loc_18002ACC1
0x18002aca7  mov     ecx, [rsp+68h+arg_8]
0x18002acab  mov     rdx, [rsp+68h+arg_20]
0x18002acb3  mov     [r14], ecx
0x18002acb6  mov     ecx, [rsp+68h+cb]
0x18002acba  mov     [rsi], rdi
0x18002acbd  mov     [rdx], ecx
0x18002acbf  jmp     short loc_18002ACD1
0x18002acc1  mov     rcx, rdi; pv
0x18002acc4  call    cs:__imp_CoTaskMemFree
0x18002acca  jmp     short loc_18002ACD1
0x18002accc  mov     ebx, 8007000Eh
0x18002acd1  mov     eax, ebx
0x18002acd3  add     rsp, 48h
0x18002acd7  pop     r14
0x18002acd9  pop     rdi
0x18002acda  pop     rsi
0x18002acdb  pop     rbx
0x18002acdc  retn
```
