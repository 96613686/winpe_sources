# FmtEnumInfoList_Clear(PSFORMAT_ENUMINFOLIST *)

- ea: `0x18002bc2c`
- end: `0x18002bcc0`
- name: `?FmtEnumInfoList_Clear@@YAXPEAUPSFORMAT_ENUMINFOLIST@@@Z`
- size: `148`
- prototype: `void __fastcall(struct PSFORMAT_ENUMINFOLIST *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c1a0`
- `0x18000cee0`
- `0x18002ac3c`
- `0x18002ae2c`
- `0x18002c28c`
- `0x18002daac`

## callees

- `0x18002bc2c`
- `0x18002cd24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bcb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bcb0`

## pseudocode

```c
void __fastcall FmtEnumInfoList_Clear(struct PSFORMAT_ENUMINFOLIST *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  unsigned int i; // edi

  if ( *((_QWORD *)a1 + 1) )
  {
    for ( i = 0; i < *(_DWORD *)a1; ++i )
      EnumInfo_Clear((PROPVARIANT *)(*((_QWORD *)a1 + 1) + 112LL * i));
    CoTaskMemFree(*((LPVOID *)a1 + 1));
    *((_QWORD *)a1 + 1) = 0;
  }
  v2 = (void *)*((_QWORD *)a1 + 3);
  *(_DWORD *)a1 = 0;
  CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)a1 + 4);
  *((_QWORD *)a1 + 3) = 0;
  *(_DWORD *)a1 = 0;
  *((_QWORD *)a1 + 7) = 0;
  *((_QWORD *)a1 + 6) = 0;
  CoTaskMemFree(v3);
  *((_QWORD *)a1 + 4) = 0;
  *((_WORD *)a1 + 20) = 0;
}

```

## disassembly

```asm
0x18002bc2c  mov     [rsp+arg_0], rbx
0x18002bc31  push    rdi
0x18002bc32  sub     rsp, 20h
0x18002bc36  cmp     qword ptr [rcx+8], 0
0x18002bc3b  mov     rbx, rcx
0x18002bc3e  jnz     short loc_18002BC91
0x18002bc40  mov     rcx, [rbx+18h]; pv
0x18002bc44  mov     dword ptr [rbx], 0
0x18002bc4a  call    cs:__imp_CoTaskMemFree
0x18002bc50  mov     rcx, [rbx+20h]; pv
0x18002bc54  mov     qword ptr [rbx+18h], 0
0x18002bc5c  mov     dword ptr [rbx], 0
0x18002bc62  mov     qword ptr [rbx+38h], 0
0x18002bc6a  mov     qword ptr [rbx+30h], 0
0x18002bc72  call    cs:__imp_CoTaskMemFree
0x18002bc78  xor     eax, eax
0x18002bc7a  mov     qword ptr [rbx+20h], 0
0x18002bc82  mov     [rbx+28h], ax
0x18002bc86  mov     rbx, [rsp+28h+arg_0]
0x18002bc8b  add     rsp, 20h
0x18002bc8f  pop     rdi
0x18002bc90  retn
0x18002bc91  xor     edi, edi
0x18002bc93  cmp     [rcx], edi
0x18002bc95  jbe     short loc_18002BCAC
0x18002bc97  mov     eax, edi
0x18002bc99  imul    rcx, rax, 70h ; 'p'
0x18002bc9d  add     rcx, [rbx+8]; struct PSFORMAT_ENUMINFO *
0x18002bca1  call    ?EnumInfo_Clear@@YAXPEAUPSFORMAT_ENUMINFO@@@Z; EnumInfo_Clear(PSFORMAT_ENUMINFO *)
0x18002bca6  inc     edi
0x18002bca8  cmp     edi, [rbx]
0x18002bcaa  jb      short loc_18002BC97
0x18002bcac  mov     rcx, [rbx+8]; pv
0x18002bcb0  call    cs:__imp_CoTaskMemFree
0x18002bcb6  mov     qword ptr [rbx+8], 0
0x18002bcbe  jmp     short loc_18002BC40
```
