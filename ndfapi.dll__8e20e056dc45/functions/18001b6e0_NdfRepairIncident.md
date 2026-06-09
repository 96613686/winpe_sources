# NdfRepairIncident

- ea: `0x18001b6e0`
- end: `0x18001b78d`
- name: `NdfRepairIncident`
- size: `173`
- prototype: `HRESULT __stdcall(NDFHANDLE Handle, RepairInfoEx *RepairEx, DWORD dwWait)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000721c`
- `0x1800098b0`
- `0x18001a6b4`
- `0x18001b6e0`

## import_xrefs

- `wdi!WdiCancel` at `0x18001b72f`
- `wdi!WdiCancel` at `0x18001b72f`

## string_xrefs

- `0x18001b713`: `NdfRepairIncident`

## pseudocode

```c
HRESULT __stdcall NdfRepairIncident(NDFHANDLE Handle, RepairInfoEx *RepairEx, DWORD dwWait)
{
  size_t v7[5]; // [rsp+30h] [rbp-28h] BYREF

  v7[3] = 15;
  v7[2] = 0;
  LOBYTE(v7[0]) = 0;
  std::string::assign(v7, "NdfRepairIncident", 0x11u);
  TelemeterAPICall(v7);
  if ( (unsigned int)WdiCancel(0) != -2147023611
    && Handle
    && *(_QWORD *)Handle == 0x49EE979964EB97E9LL
    && *((_QWORD *)Handle + 1) == 0xC1B5FAFE15B09CBBuLL )
  {
    return CNetDiagClient::RepairWithoutUI(Handle, RepairEx, dwWait, 1, 0);
  }
  else
  {
    return -2147024890;
  }
}

```

## disassembly

```asm
0x18001b6e0  mov     rax, rsp
0x18001b6e3  mov     [rax+8], rbx
0x18001b6e7  mov     [rax+10h], rsi
0x18001b6eb  push    rdi
0x18001b6ec  sub     rsp, 50h
0x18001b6f0  mov     edi, r8d
0x18001b6f3  mov     qword ptr [rax-10h], 0Fh
0x18001b6fb  mov     rsi, rdx
0x18001b6fe  mov     qword ptr [rax-18h], 0
0x18001b706  mov     rbx, rcx
0x18001b709  mov     byte ptr [rax-28h], 0
0x18001b70d  mov     r8d, 11h; Size
0x18001b713  lea     rdx, aNdfrepairincid_1; "NdfRepairIncident"
0x18001b71a  lea     rcx, [rax-28h]; void *
0x18001b71e  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18001b723  lea     rcx, [rsp+58h+var_28]
0x18001b728  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18001b72d  xor     ecx, ecx
0x18001b72f  call    cs:__imp_WdiCancel
0x18001b735  cmp     eax, 80070505h
0x18001b73a  jz      short loc_18001B778
0x18001b73c  test    rbx, rbx
0x18001b73f  jz      short loc_18001B778
0x18001b741  mov     rax, [rbx]
0x18001b744  cmp     rax, cs:qword_180027A50
0x18001b74b  jnz     short loc_18001B778
0x18001b74d  mov     rax, [rbx+8]
0x18001b751  cmp     rax, cs:qword_180027A58
0x18001b758  jnz     short loc_18001B778
0x18001b75a  mov     r9d, 1
0x18001b760  mov     [rsp+58h+var_38], 0
0x18001b768  mov     r8d, edi
0x18001b76b  mov     rdx, rsi
0x18001b76e  mov     rcx, rbx
0x18001b771  call    ?RepairWithoutUI@CNetDiagClient@@QEAAJPEAUtagRepairInfoEx@@KHW4NDFRepairState@@@Z; CNetDiagClient::RepairWithoutUI(tagRepairInfoEx *,ulong,int,NDFRepairState)
0x18001b776  jmp     short loc_18001B77D
0x18001b778  mov     eax, 80070006h
0x18001b77d  mov     rbx, [rsp+58h+arg_0]
0x18001b782  mov     rsi, [rsp+58h+arg_8]
0x18001b787  add     rsp, 50h
0x18001b78b  pop     rdi
0x18001b78c  retn
```
