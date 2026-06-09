# FwRegNotifyCreateKey(FW_REG_NOTIFY_ *)

- ea: `0x180002440`
- end: `0x180002498`
- name: `?FwRegNotifyCreateKey@@YAJPEAUFW_REG_NOTIFY_@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(struct FW_REG_NOTIFY_ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800023c0`

## callees

- `0x180002440`
- `0x1800028e0`
- `0x1800031a0`
- `0x1800047e0`

## string_xrefs

- `0x18000248a`: `FwRegNotifyCreateKey`

## pseudocode

```c
__int64 __fastcall FwRegNotifyCreateKey(struct FW_REG_NOTIFY_ *a1)
{
  HKEY *v1; // rbx
  const WCHAR *v3; // rdx
  HKEY v4; // rcx
  int Key; // eax
  unsigned int v6; // ebx

  v1 = (HKEY *)((char *)a1 + 48);
  FwRegCloseKey(*((_QWORD *)a1 + 6));
  v3 = (const WCHAR *)*((_QWORD *)a1 + 1);
  v4 = *(HKEY *)a1;
  *v1 = 0;
  Key = FwRegCreateKey(v4, v3, 0x10u, v1);
  v6 = Key;
  if ( Key < 0 )
    FwReportReturnError("FwRegNotifyCreateKey", (unsigned int)Key);
  return v6;
}

```

## disassembly

```asm
0x180002440  mov     [rsp+arg_0], rbx
0x180002445  push    rdi
0x180002446  sub     rsp, 20h
0x18000244a  lea     rbx, [rcx+30h]
0x18000244e  mov     rdi, rcx
0x180002451  mov     rcx, [rbx]
0x180002454  call    FwRegCloseKey
0x180002459  mov     rdx, [rdi+8]; lpSubKey
0x18000245d  mov     r9, rbx
0x180002460  mov     rcx, [rdi]; hKey
0x180002463  mov     r8d, 10h; samDesired
0x180002469  mov     qword ptr [rbx], 0
0x180002470  call    FwRegCreateKey
0x180002475  mov     ebx, eax
0x180002477  test    eax, eax
0x180002479  js      short loc_180002488
0x18000247b  mov     eax, ebx
0x18000247d  mov     rbx, [rsp+28h+arg_0]
0x180002482  add     rsp, 20h
0x180002486  pop     rdi
0x180002487  retn
0x180002488  mov     edx, ebx
0x18000248a  lea     rcx, aFwregnotifycre_1; "FwRegNotifyCreateKey"
0x180002491  call    FwReportReturnError
0x180002496  jmp     short loc_18000247B
```
