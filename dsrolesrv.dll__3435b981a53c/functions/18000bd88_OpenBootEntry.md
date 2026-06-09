# OpenBootEntry

- ea: `0x18000bd88`
- end: `0x18000be04`
- name: `OpenBootEntry`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b1c8`
- `0x18000b6b0`

## callees

- `0x18000bd88`
- `0x180020dbc`

## import_xrefs

- `bcd!BcdOpenObject` at `0x18000bdc7`
- `bcd!BcdOpenObject` at `0x18000bdc7`
- `bcd!BcdOpenSystemStore` at `0x18000bda3`
- `bcd!BcdOpenSystemStore` at `0x18000bda3`
- `bcd!BcdCloseStore` at `0x18000bdf1`
- `bcd!BcdCloseStore` at `0x18000bdf1`

## string_xrefs

- `0x18000bdaf`: `vDC Cloning: Cannot open the system BCD store, NTSTATUS code: 0x%x\n`
- `0x18000bdd3`: `vDC Cloning: Cannot open the default boot entry for the Windows Boot, NTSTATUS code: 0x%x\n`

## pseudocode

```c
__int64 __fastcall OpenBootEntry(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  v2 = BcdOpenSystemStore(&v6);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = BcdOpenObject(v6, &GUID_CURRENT_BOOT_ENTRY, a1);
    v3 = v4;
    if ( v4 < 0 )
      DsRolepLogPrintRoutine(
        1,
        "vDC Cloning: Cannot open the default boot entry for the Windows Boot, NTSTATUS code: 0x%x\n",
        (unsigned int)v4);
  }
  else
  {
    DsRolepLogPrintRoutine(1, "vDC Cloning: Cannot open the system BCD store, NTSTATUS code: 0x%x\n", (unsigned int)v2);
  }
  if ( v6 )
    BcdCloseStore();
  return v3;
}

```

## disassembly

```asm
0x18000bd88  mov     [rsp+arg_0], rbx
0x18000bd8d  push    rdi
0x18000bd8e  sub     rsp, 20h
0x18000bd92  mov     rdi, rcx
0x18000bd95  mov     [rsp+28h+arg_8], 0
0x18000bd9e  lea     rcx, [rsp+28h+arg_8]
0x18000bda3  call    cs:__imp_BcdOpenSystemStore
0x18000bda9  mov     ebx, eax
0x18000bdab  test    eax, eax
0x18000bdad  jns     short loc_18000BDB8
0x18000bdaf  lea     rdx, aVdcCloningCann_0; "vDC Cloning: Cannot open the system BCD"...
0x18000bdb6  jmp     short loc_18000BDDA
0x18000bdb8  mov     rcx, [rsp+28h+arg_8]
0x18000bdbd  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x18000bdc4  mov     r8, rdi
0x18000bdc7  call    cs:__imp_BcdOpenObject
0x18000bdcd  mov     ebx, eax
0x18000bdcf  test    eax, eax
0x18000bdd1  jns     short loc_18000BDE7
0x18000bdd3  lea     rdx, aVdcCloningCann_1; "vDC Cloning: Cannot open the default bo"...
0x18000bdda  mov     r8d, eax
0x18000bddd  mov     ecx, 1
0x18000bde2  call    DsRolepLogPrintRoutine
0x18000bde7  mov     rcx, [rsp+28h+arg_8]
0x18000bdec  test    rcx, rcx
0x18000bdef  jz      short loc_18000BDF7
0x18000bdf1  call    cs:__imp_BcdCloseStore
0x18000bdf7  mov     eax, ebx
0x18000bdf9  mov     rbx, [rsp+28h+arg_0]
0x18000bdfe  add     rsp, 20h
0x18000be02  pop     rdi
0x18000be03  retn
```
