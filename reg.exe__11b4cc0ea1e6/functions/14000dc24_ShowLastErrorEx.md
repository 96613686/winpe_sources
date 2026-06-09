# ShowLastErrorEx

- ea: `0x14000dc24`
- end: `0x14000dcda`
- name: `ShowLastErrorEx`
- size: `182`
- prototype: ``
- caller_count: `16`
- callee_count: `6`
- tags: ``

## callers

- `0x1400030b8`
- `0x14000329c`
- `0x14000375c`
- `0x140003ec4`
- `0x140004518`
- `0x140004708`
- `0x140004a38`
- `0x140005bac`
- `0x140006394`
- `0x140006f9c`
- `0x140007170`
- `0x140007834`
- `0x140008788`
- `0x1400096a8`
- `0x14000998c`
- `0x140009ec0`

## callees

- `0x14000ccc4`
- `0x14000cd10`
- `0x14000d978`
- `0x14000dc24`
- `0x14000dce0`
- `0x14000e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dcb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dcb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dcc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dcc2`

## pseudocode

```c
__int64 __fastcall ShowLastErrorEx(FILE *Stream, int a2)
{
  char v2; // bl
  __int64 v4; // rcx
  __int64 ResString; // rax
  const WCHAR *Reason; // rax

  v2 = a2;
  if ( Stream && (a2 & 0xF0000) != 0 )
  {
    if ( (a2 & 0x10000) != 0 )
      SaveLastError();
    if ( (v2 & 1) != 0 )
    {
      v4 = 5001;
    }
    else if ( (v2 & 4) != 0 )
    {
      v4 = 5002;
    }
    else if ( (v2 & 2) != 0 )
    {
      v4 = 5004;
    }
    else
    {
      if ( (v2 & 8) == 0 )
      {
LABEL_14:
        Reason = (const WCHAR *)GetReason();
        ShowMessage(Stream, Reason);
        return 1;
      }
      v4 = 5003;
    }
    ResString = GetResString(v4);
    ShowMessageEx(Stream, 1, 1, L"%s ", ResString);
    goto LABEL_14;
  }
  if ( !GetLastError() )
    SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x14000dc24  mov     [rsp+arg_0], rbx
0x14000dc29  mov     [rsp+arg_8], rsi
0x14000dc2e  push    rdi
0x14000dc2f  sub     rsp, 30h
0x14000dc33  mov     ebx, edx
0x14000dc35  mov     rdi, rcx
0x14000dc38  test    rcx, rcx
0x14000dc3b  jz      short loc_14000DCB5
0x14000dc3d  test    edx, 0F0000h
0x14000dc43  jz      short loc_14000DCB5
0x14000dc45  bt      edx, 10h
0x14000dc49  jnb     short loc_14000DC50
0x14000dc4b  call    SaveLastError
0x14000dc50  mov     esi, 1
0x14000dc55  test    sil, bl
0x14000dc58  jz      short loc_14000DC61
0x14000dc5a  mov     ecx, 1389h
0x14000dc5f  jmp     short loc_14000DC83
0x14000dc61  test    bl, 4
0x14000dc64  jz      short loc_14000DC6D
0x14000dc66  mov     ecx, 138Ah
0x14000dc6b  jmp     short loc_14000DC83
0x14000dc6d  test    bl, 2
0x14000dc70  jz      short loc_14000DC79
0x14000dc72  mov     ecx, 138Ch
0x14000dc77  jmp     short loc_14000DC83
0x14000dc79  test    bl, 8
0x14000dc7c  jz      short loc_14000DCA1
0x14000dc7e  mov     ecx, 138Bh
0x14000dc83  call    GetResString
0x14000dc88  lea     r9, aS_2; "%s "
0x14000dc8f  mov     [rsp+38h+var_18], rax
0x14000dc94  mov     r8d, esi
0x14000dc97  mov     edx, esi
0x14000dc99  mov     rcx, rdi
0x14000dc9c  call    ShowMessageEx
0x14000dca1  call    GetReason
0x14000dca6  mov     rdx, rax; lpString
0x14000dca9  mov     rcx, rdi; Stream
0x14000dcac  call    ShowMessage
0x14000dcb1  mov     eax, esi
0x14000dcb3  jmp     short loc_14000DCCA
0x14000dcb5  call    cs:__imp_GetLastError
0x14000dcbb  test    eax, eax
0x14000dcbd  jnz     short loc_14000DCC8
0x14000dcbf  lea     ecx, [rax+57h]; dwErrCode
0x14000dcc2  call    cs:__imp_SetLastError
0x14000dcc8  xor     eax, eax
0x14000dcca  mov     rbx, [rsp+38h+arg_0]
0x14000dccf  mov     rsi, [rsp+38h+arg_8]
0x14000dcd4  add     rsp, 30h
0x14000dcd8  pop     rdi
0x14000dcd9  retn
```
