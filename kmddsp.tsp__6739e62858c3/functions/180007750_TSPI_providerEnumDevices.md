# TSPI_providerEnumDevices

- ea: `0x180007750`
- end: `0x1800077ae`
- name: `TSPI_providerEnumDevices`
- size: `94`
- prototype: `LONG __stdcall(DWORD dwPermanentProviderID, LPDWORD lpdwNumLines, LPDWORD lpdwNumPhones, HPROVIDER hProvider, LINEEVENT lpfnLineCreateProc, PHONEEVENT lpfnPhoneCreateProc)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007df8`

## pseudocode

```c
LONG __stdcall TSPI_providerEnumDevices(
        DWORD dwPermanentProviderID,
        LPDWORD lpdwNumLines,
        LPDWORD lpdwNumPhones,
        HPROVIDER hProvider,
        LINEEVENT lpfnLineCreateProc,
        PHONEEVENT lpfnPhoneCreateProc)
{
  LONG result; // eax

  TspLog(8, "providerEnumDevices: permProvID(%x)", dwPermanentProviderID);
  *lpdwNumLines = 0;
  gpfnLineEvent = (__int64)lpfnLineCreateProc;
  result = 0;
  ghProvider = (__int64)hProvider;
  *lpdwNumPhones = 0;
  return result;
}

```

## disassembly

```asm
0x180007750  mov     [rsp+arg_0], rbx
0x180007755  mov     [rsp+arg_8], rsi
0x18000775a  push    rdi
0x18000775b  sub     rsp, 20h
0x18000775f  mov     rdi, r8
0x180007762  mov     rbx, rdx
0x180007765  mov     r8d, ecx
0x180007768  lea     rdx, aProviderenumde; "providerEnumDevices: permProvID(%x)"
0x18000776f  mov     ecx, 8
0x180007774  mov     rsi, r9
0x180007777  call    TspLog
0x18000777c  mov     rax, [rsp+28h+lpfnLineCreateProc]
0x180007781  mov     dword ptr [rbx], 0
0x180007787  mov     rbx, [rsp+28h+arg_0]
0x18000778c  mov     cs:gpfnLineEvent, rax
0x180007793  xor     eax, eax
0x180007795  mov     cs:ghProvider, rsi
0x18000779c  mov     rsi, [rsp+28h+arg_8]
0x1800077a1  mov     dword ptr [rdi], 0
0x1800077a7  add     rsp, 20h
0x1800077ab  pop     rdi
0x1800077ac  retn
```
