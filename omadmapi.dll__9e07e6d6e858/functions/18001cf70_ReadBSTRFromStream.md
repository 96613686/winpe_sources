# ReadBSTRFromStream

- ea: `0x18001cf70`
- end: `0x18001d06c`
- name: `ReadBSTRFromStream`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001d1b0`

## callees

- `0x1800031d4`
- `0x1800036cc`
- `0x18001cf70`
- `0x180024010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d04f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d04f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001d031`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001d031`

## pseudocode

```c
__int64 __fastcall ReadBSTRFromStream(BSTR *a1, __int64 a2)
{
  CHAR *v2; // rdi
  int v5; // ebx
  CHAR *v6; // rax
  BSTR v7; // rax
  UINT len; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  len = 0;
  v10 = 0;
  if ( a1 && a2 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, UINT *, __int64, int *))(*(_QWORD *)a2 + 24LL))(a2, &len, 4, &v10);
    if ( v5 >= 0 )
    {
      if ( v10 == 4 && (len & 1) == 0 )
      {
        v6 = (CHAR *)operator new[](len, (const struct std::nothrow_t *)&std::nothrow);
        v2 = v6;
        if ( !v6 )
        {
LABEL_9:
          v5 = -2147024882;
          goto LABEL_14;
        }
        v5 = (*(__int64 (__fastcall **)(__int64, CHAR *, _QWORD, int *))(*(_QWORD *)a2 + 24LL))(a2, v6, len, &v10);
        if ( v5 < 0 )
          goto LABEL_14;
        if ( len == v10 )
        {
          v7 = SysAllocStringByteLen(v2, len);
          if ( v7 )
          {
            *a1 = v7;
            goto LABEL_14;
          }
          goto LABEL_9;
        }
      }
      v5 = -2147467259;
    }
  }
  else
  {
    v5 = -2147467261;
  }
LABEL_14:
  operator delete(v2);
  SysFreeString(0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001cf70  mov     [rsp+arg_8], rbx
0x18001cf75  push    rsi
0x18001cf76  push    rdi
0x18001cf77  push    r14
0x18001cf79  sub     rsp, 30h
0x18001cf7d  xor     edi, edi
0x18001cf7f  mov     [rsp+48h+len], 0
0x18001cf87  mov     [rsp+48h+arg_10], 0
0x18001cf8f  mov     rsi, rdx
0x18001cf92  mov     r14, rcx
0x18001cf95  test    rcx, rcx
0x18001cf98  jnz     short loc_18001CFA4
0x18001cf9a  mov     ebx, 80004003h
0x18001cf9f  jmp     loc_18001D045
0x18001cfa4  test    rsi, rsi
0x18001cfa7  jz      short loc_18001CF9A
0x18001cfa9  mov     rax, [rdx]
0x18001cfac  lea     r9, [rsp+48h+arg_10]
0x18001cfb1  mov     r8d, 4
0x18001cfb7  lea     rdx, [rsp+48h+len]
0x18001cfbc  mov     rcx, rsi
0x18001cfbf  mov     rax, [rax+18h]
0x18001cfc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfc8  mov     ebx, eax
0x18001cfca  test    eax, eax
0x18001cfcc  js      short loc_18001D045
0x18001cfce  cmp     [rsp+48h+arg_10], 4
0x18001cfd3  jz      short loc_18001CFDC
0x18001cfd5  mov     ebx, 80004005h
0x18001cfda  jmp     short loc_18001D045
0x18001cfdc  test    byte ptr [rsp+48h+len], 1
0x18001cfe1  jnz     short loc_18001CFD5
0x18001cfe3  mov     ecx, [rsp+48h+len]; unsigned __int64
0x18001cfe7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001cfee  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001cff3  mov     rdi, rax
0x18001cff6  test    rax, rax
0x18001cff9  jnz     short loc_18001D002
0x18001cffb  mov     ebx, 8007000Eh
0x18001d000  jmp     short loc_18001D045
0x18001d002  mov     rax, [rsi]
0x18001d005  lea     r9, [rsp+48h+arg_10]
0x18001d00a  mov     r8d, [rsp+48h+len]
0x18001d00f  mov     rdx, rdi
0x18001d012  mov     rcx, rsi
0x18001d015  mov     rax, [rax+18h]
0x18001d019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d01e  mov     ebx, eax
0x18001d020  test    eax, eax
0x18001d022  js      short loc_18001D045
0x18001d024  mov     edx, [rsp+48h+len]; len
0x18001d028  cmp     edx, [rsp+48h+arg_10]
0x18001d02c  jnz     short loc_18001CFD5
0x18001d02e  mov     rcx, rdi; psz
0x18001d031  call    cs:__imp_SysAllocStringByteLen
0x18001d038  nop     dword ptr [rax+rax+00h]
0x18001d03d  test    rax, rax
0x18001d040  jz      short loc_18001CFFB
0x18001d042  mov     [r14], rax
0x18001d045  mov     rcx, rdi; void *
0x18001d048  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d04d  xor     ecx, ecx; bstrString
0x18001d04f  call    cs:__imp_SysFreeString
0x18001d056  nop     dword ptr [rax+rax+00h]
0x18001d05b  mov     eax, ebx
0x18001d05d  mov     rbx, [rsp+48h+arg_8]
0x18001d062  add     rsp, 30h
0x18001d066  pop     r14
0x18001d068  pop     rdi
0x18001d069  pop     rsi
0x18001d06a  retn
```
