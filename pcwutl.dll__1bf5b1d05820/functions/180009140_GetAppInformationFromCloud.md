# GetAppInformationFromCloud

- ea: `0x180009140`
- end: `0x1800091ed`
- name: `GetAppInformationFromCloud`
- size: `173`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800039c8`
- `0x18000e240`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180009192`
- `KERNEL32!GetTickCount64` at `0x1800091a8`
- `KERNEL32!GetTickCount64` at `0x180009192`
- `KERNEL32!GetTickCount64` at `0x1800091a8`

## string_xrefs

- `0x180009155`: `In GetAppInformationFromCloud, path: %ws`
- `0x1800091b2`: `Completed OneSettings query with time: %d; layer: %ws; result: 0x%x`

## pseudocode

```c
__int64 __fastcall GetAppInformationFromCloud(
        unsigned __int16 *a1,
        _WORD *a2,
        _DWORD *a3,
        unsigned __int16 *a4,
        _DWORD *a5)
{
  __int64 v10; // [rsp+20h] [rbp-48h]
  int v11; // [rsp+30h] [rbp-38h]

  AslLogCallPrintf(3, "GetAppInformationFromCloud", 1438, "In GetAppInformationFromCloud, path: %ws", a1);
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  LODWORD(a2) = GetTickCount64();
  LODWORD(a3) = GetOnesettingsValues(a1, a4);
  v11 = (int)a3;
  LODWORD(v10) = GetTickCount64() - (_DWORD)a2;
  AslLogCallPrintf(
    3,
    "GetAppInformationFromCloud",
    1455,
    "Completed OneSettings query with time: %d; layer: %ws; result: 0x%x",
    v10,
    a4,
    v11);
  return ((int)a3 >> 31) & 0x3A;
}

```

## disassembly

```asm
0x180009140  push    rbx
0x180009142  push    rsi
0x180009143  push    rdi
0x180009144  push    r14
0x180009146  sub     rsp, 48h
0x18000914a  mov     r14, r9
0x18000914d  mov     [rsp+68h+var_48], rcx
0x180009152  mov     rdi, r8
0x180009155  lea     r9, aInGetappinform; "In GetAppInformationFromCloud, path: %w"...
0x18000915c  mov     rbx, rdx
0x18000915f  mov     rsi, rcx
0x180009162  mov     r8d, 59Eh
0x180009168  lea     rdx, aGetappinformat_0; "GetAppInformationFromCloud"
0x18000916f  mov     ecx, 3
0x180009174  call    AslLogCallPrintf
0x180009179  xor     eax, eax
0x18000917b  mov     [rbx], ax
0x18000917e  mov     [rdi], eax
0x180009180  mov     [r14], ax
0x180009184  mov     rax, [rsp+68h+arg_20]
0x18000918c  mov     dword ptr [rax], 0
0x180009192  call    cs:__imp_GetTickCount64
0x180009198  mov     rdx, r14; unsigned __int16 *
0x18000919b  mov     rcx, rsi; unsigned __int16 *
0x18000919e  mov     rbx, rax
0x1800091a1  call    ?GetOnesettingsValues@@YAJPEBGPEAG@Z; GetOnesettingsValues(ushort const *,ushort *)
0x1800091a6  mov     edi, eax
0x1800091a8  call    cs:__imp_GetTickCount64
0x1800091ae  mov     [rsp+68h+var_38], edi
0x1800091b2  lea     r9, aCompletedOnese; "Completed OneSettings query with time: "...
0x1800091b9  sub     eax, ebx
0x1800091bb  mov     [rsp+68h+var_40], r14
0x1800091c0  mov     r8d, 5AFh
0x1800091c6  mov     dword ptr [rsp+68h+var_48], eax
0x1800091ca  lea     rdx, aGetappinformat_0; "GetAppInformationFromCloud"
0x1800091d1  mov     ecx, 3
0x1800091d6  call    AslLogCallPrintf
0x1800091db  sar     edi, 1Fh
0x1800091de  and     edi, 3Ah
0x1800091e1  mov     eax, edi
0x1800091e3  add     rsp, 48h
0x1800091e7  pop     r14
0x1800091e9  pop     rdi
0x1800091ea  pop     rsi
0x1800091eb  pop     rbx
0x1800091ec  retn
```
