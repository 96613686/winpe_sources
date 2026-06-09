# ShowLastErrorEx

- ea: `0x14000e798`
- end: `0x14000e85b`
- name: `ShowLastErrorEx`
- size: `195`
- prototype: ``
- caller_count: `16`
- callee_count: `6`
- tags: ``

## callers

- `0x1400031f4`
- `0x1400033d8`
- `0x1400038f8`
- `0x1400040b8`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`
- `0x140005ef0`
- `0x14000672c`
- `0x1400073d4`
- `0x1400075ac`
- `0x140007cbc`
- `0x140008cbc`
- `0x140009c68`
- `0x140009f80`
- `0x14000a4e4`

## callees

- `0x14000d610`
- `0x14000d65c`
- `0x14000e484`
- `0x14000e798`
- `0x14000e864`
- `0x14000ec2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e829`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e83c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e83c`

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
0x14000e798  mov     [rsp+arg_0], rbx
0x14000e79d  mov     [rsp+arg_8], rsi
0x14000e7a2  push    rdi
0x14000e7a3  sub     rsp, 30h
0x14000e7a7  mov     ebx, edx
0x14000e7a9  mov     rdi, rcx
0x14000e7ac  test    rcx, rcx
0x14000e7af  jz      short loc_14000E829
0x14000e7b1  test    edx, 0F0000h
0x14000e7b7  jz      short loc_14000E829
0x14000e7b9  bt      edx, 10h
0x14000e7bd  jnb     short loc_14000E7C4
0x14000e7bf  call    SaveLastError
0x14000e7c4  mov     esi, 1
0x14000e7c9  test    sil, bl
0x14000e7cc  jz      short loc_14000E7D5
0x14000e7ce  mov     ecx, 1389h
0x14000e7d3  jmp     short loc_14000E7F7
0x14000e7d5  test    bl, 4
0x14000e7d8  jz      short loc_14000E7E1
0x14000e7da  mov     ecx, 138Ah
0x14000e7df  jmp     short loc_14000E7F7
0x14000e7e1  test    bl, 2
0x14000e7e4  jz      short loc_14000E7ED
0x14000e7e6  mov     ecx, 138Ch
0x14000e7eb  jmp     short loc_14000E7F7
0x14000e7ed  test    bl, 8
0x14000e7f0  jz      short loc_14000E815
0x14000e7f2  mov     ecx, 138Bh
0x14000e7f7  call    GetResString
0x14000e7fc  lea     r9, aS_2; "%s "
0x14000e803  mov     [rsp+38h+var_18], rax
0x14000e808  mov     r8d, esi
0x14000e80b  mov     edx, esi
0x14000e80d  mov     rcx, rdi
0x14000e810  call    ShowMessageEx
0x14000e815  call    GetReason
0x14000e81a  mov     rdx, rax; lpString
0x14000e81d  mov     rcx, rdi; Stream
0x14000e820  call    ShowMessage
0x14000e825  mov     eax, esi
0x14000e827  jmp     short loc_14000E84A
0x14000e829  call    cs:__imp_GetLastError
0x14000e830  nop     dword ptr [rax+rax+00h]
0x14000e835  test    eax, eax
0x14000e837  jnz     short loc_14000E848
0x14000e839  lea     ecx, [rax+57h]; dwErrCode
0x14000e83c  call    cs:__imp_SetLastError
0x14000e843  nop     dword ptr [rax+rax+00h]
0x14000e848  xor     eax, eax
0x14000e84a  mov     rbx, [rsp+38h+arg_0]
0x14000e84f  mov     rsi, [rsp+38h+arg_8]
0x14000e854  add     rsp, 30h
0x14000e858  pop     rdi
0x14000e859  retn
```
