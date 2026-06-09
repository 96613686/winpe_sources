# SetVariantAsByteArray(tagVARIANT *,ulong,uchar *)

- ea: `0x18000db64`
- end: `0x18000dc02`
- name: `?SetVariantAsByteArray@@YAJPEAUtagVARIANT@@KPEAE@Z`
- size: `158`
- prototype: `int(struct tagVARIANT *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bd80`
- `0x18000c0ac`

## callees

- `0x18000db64`
- `0x1800111a2`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000dba7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000dba7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000dbc5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000dbc5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000dbea`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000dbea`

## pseudocode

```c
__int64 __fastcall SetVariantAsByteArray(struct tagVARIANT *a1, unsigned int a2, unsigned __int8 *a3)
{
  size_t v3; // rdi
  SAFEARRAY *v6; // rax
  unsigned __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  void *ppvData; // [rsp+48h] [rbp+20h] BYREF

  v3 = a2;
  a1->vt = 8209;
  a1->llVal = 0;
  ppvData = 0;
  v8 = a2;
  v6 = SafeArrayCreate(0x11u, 1u, (SAFEARRAYBOUND *)&v8);
  a1->llVal = (LONGLONG)v6;
  if ( !v6 )
    return 2147942414LL;
  if ( SafeArrayAccessData(v6, &ppvData) < 0 )
    return 2147549183LL;
  memcpy_0(ppvData, a3, v3);
  SafeArrayUnaccessData(a1->parray);
  return 0;
}

```

## disassembly

```asm
0x18000db64  mov     rax, rsp
0x18000db67  mov     [rax+10h], rbx
0x18000db6b  mov     [rax+18h], rsi
0x18000db6f  push    rdi
0x18000db70  sub     rsp, 20h
0x18000db74  mov     edi, edx
0x18000db76  mov     rbx, rcx
0x18000db79  mov     word ptr [rcx], 2011h
0x18000db7e  mov     rsi, r8
0x18000db81  mov     qword ptr [rcx+8], 0
0x18000db89  lea     r8, [rax+8]; rgsabound
0x18000db8d  mov     ecx, 11h; vt
0x18000db92  mov     qword ptr [rax+20h], 0
0x18000db9a  mov     dword ptr [rax+0Ch], 0
0x18000dba1  mov     [rax+8], edi
0x18000dba4  lea     edx, [rcx-10h]; cDims
0x18000dba7  call    cs:__imp_SafeArrayCreate
0x18000dbad  mov     [rbx+8], rax
0x18000dbb1  test    rax, rax
0x18000dbb4  jnz     short loc_18000DBBD
0x18000dbb6  mov     eax, 8007000Eh
0x18000dbbb  jmp     short loc_18000DBF2
0x18000dbbd  lea     rdx, [rsp+28h+ppvData]; ppvData
0x18000dbc2  mov     rcx, rax; psa
0x18000dbc5  call    cs:__imp_SafeArrayAccessData
0x18000dbcb  test    eax, eax
0x18000dbcd  jns     short loc_18000DBD6
0x18000dbcf  mov     eax, 8000FFFFh
0x18000dbd4  jmp     short loc_18000DBF2
0x18000dbd6  mov     rcx, [rsp+28h+ppvData]; void *
0x18000dbdb  mov     r8, rdi; Size
0x18000dbde  mov     rdx, rsi; Src
0x18000dbe1  call    memcpy_0
0x18000dbe6  mov     rcx, [rbx+8]; psa
0x18000dbea  call    cs:__imp_SafeArrayUnaccessData
0x18000dbf0  xor     eax, eax
0x18000dbf2  mov     rbx, [rsp+28h+arg_8]
0x18000dbf7  mov     rsi, [rsp+28h+arg_10]
0x18000dbfc  add     rsp, 20h
0x18000dc00  pop     rdi
0x18000dc01  retn
```
