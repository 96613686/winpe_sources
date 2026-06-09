# UpdateJobType

- ea: `0x180006fa8`
- end: `0x1800071ed`
- name: `UpdateJobType`
- size: `581`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180005a14`

## callees

- `0x180002e7c`
- `0x180003cf0`
- `0x180005548`
- `0x1800056d4`
- `0x180006fa8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000705f`
- `KERNEL32!LocalAlloc` at `0x18000705f`
- `KERNEL32!GetLastError` at `0x180007021`
- `KERNEL32!GetLastError` at `0x180007021`
- `KERNEL32!LocalFree` at `0x1800071d8`
- `KERNEL32!LocalFree` at `0x1800071d8`
- `WINSPOOL!GetJobA` at `0x180007017`
- `WINSPOOL!GetJobA` at `0x1800070ba`
- `WINSPOOL!GetJobA` at `0x180007017`
- `WINSPOOL!GetJobA` at `0x1800070ba`
- `WINSPOOL!SetJobA` at `0x1800071a1`
- `WINSPOOL!SetJobA` at `0x1800071a1`

## pseudocode

```c
__int64 __fastcall UpdateJobType(__int64 a1, void *a2)
{
  BYTE *v5; // rax
  BYTE *v6; // rdi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  unsigned int v10; // ebx
  DWORD pcbNeeded; // [rsp+70h] [rbp+8h] BYREF

  pcbNeeded = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
  if ( !GetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(a1 + 104), 2u, 0, 0, &pcbNeeded) && GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    return 20006;
  }
  v5 = (BYTE *)LocalAlloc(0, pcbNeeded);
  v6 = v5;
  if ( v5 )
  {
    if ( !GetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(a1 + 104), 2u, v5, pcbNeeded, &pcbNeeded) )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_34;
      v8 = 35;
LABEL_33:
      WPP_SF_(v7[2], v8, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
LABEL_34:
      v10 = 20006;
LABEL_36:
      LocalFree(v6);
      return v10;
    }
    if ( (unsigned int)IsPrinterDataSet(*(HANDLE *)(a1 + 96), (LPSTR)"LpdPrinterPassThrough") )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_26:
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
          WPP_SF_s(v9[2], 37, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids, *(_QWORD *)(a1 + 88));
LABEL_29:
        *(_DWORD *)(a1 + 188) = 1;
        *((_QWORD *)v6 + 6) = "RAW";
        if ( !SetJobA(*(HANDLE *)(a1 + 96), *(_DWORD *)(a1 + 104), 2u, v6, 0) )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_34;
          v8 = 38;
          goto LABEL_33;
        }
LABEL_35:
        v10 = 0;
        goto LABEL_36;
      }
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids,
        *(_QWORD *)(a1 + 88));
    }
    else if ( (unsigned int)IsPrinterDataSet(*(HANDLE *)(a1 + 96), (LPSTR)"LpdPrinterDontDetect")
           || !(unsigned int)IsDataTypeRaw(a2) )
    {
      goto LABEL_35;
    }
    v9 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
  return 20001;
}

```

## disassembly

```asm
0x180006fa8  push    rbx
0x180006faa  push    rbp
0x180006fab  push    rsi
0x180006fac  push    rdi
0x180006fad  push    r12
0x180006faf  push    r14
0x180006fb1  sub     rsp, 38h
0x180006fb5  mov     esi, r8d
0x180006fb8  mov     [rsp+68h+arg_0], 0
0x180006fc0  mov     rbp, rdx
0x180006fc3  mov     rbx, rcx
0x180006fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fcd  lea     r14, WPP_GLOBAL_Control
0x180006fd4  lea     r12, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006fdb  cmp     rcx, r14
0x180006fde  jz      short loc_180006FF7
0x180006fe0  test    byte ptr [rcx+1Ch], 1
0x180006fe4  jz      short loc_180006FF7
0x180006fe6  mov     rcx, [rcx+10h]
0x180006fea  mov     edx, 20h ; ' '
0x180006fef  mov     r8, r12
0x180006ff2  call    WPP_SF_
0x180006ff7  mov     edx, [rbx+68h]; JobId
0x180006ffa  lea     rax, [rsp+68h+arg_0]
0x180006fff  mov     rcx, [rbx+60h]; hPrinter
0x180007003  xor     r9d, r9d; pJob
0x180007006  mov     [rsp+68h+pcbNeeded], rax; pcbNeeded
0x18000700b  mov     [rsp+68h+cbBuf], 0; cbBuf
0x180007013  lea     r8d, [r9+2]; Level
0x180007017  call    cs:__imp_GetJobA
0x18000701d  test    eax, eax
0x18000701f  jnz     short loc_180007059
0x180007021  call    cs:__imp_GetLastError
0x180007027  cmp     eax, 7Ah ; 'z'
0x18000702a  jz      short loc_180007059
0x18000702c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007033  cmp     rcx, r14
0x180007036  jz      short loc_18000704F
0x180007038  test    byte ptr [rcx+1Ch], 8
0x18000703c  jz      short loc_18000704F
0x18000703e  mov     rcx, [rcx+10h]
0x180007042  mov     edx, 21h ; '!'
0x180007047  mov     r8, r12
0x18000704a  call    WPP_SF_
0x18000704f  mov     eax, 4E26h
0x180007054  jmp     loc_1800071E0
0x180007059  mov     edx, [rsp+68h+arg_0]; uBytes
0x18000705d  xor     ecx, ecx; uFlags
0x18000705f  call    cs:__imp_LocalAlloc
0x180007065  mov     rdi, rax
0x180007068  test    rax, rax
0x18000706b  jnz     short loc_180007098
0x18000706d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007074  cmp     rcx, r14
0x180007077  jz      short loc_18000708E
0x180007079  test    byte ptr [rcx+1Ch], 8
0x18000707d  jz      short loc_18000708E
0x18000707f  mov     rcx, [rcx+10h]
0x180007083  lea     edx, [rax+22h]
0x180007086  mov     r8, r12
0x180007089  call    WPP_SF_
0x18000708e  mov     eax, 4E21h
0x180007093  jmp     loc_1800071E0
0x180007098  mov     edx, [rbx+68h]; JobId
0x18000709b  lea     rax, [rsp+68h+arg_0]
0x1800070a0  mov     rcx, [rbx+60h]; hPrinter
0x1800070a4  mov     r9, rdi; pJob
0x1800070a7  mov     [rsp+68h+pcbNeeded], rax; pcbNeeded
0x1800070ac  mov     r8d, 2; Level
0x1800070b2  mov     eax, [rsp+68h+arg_0]
0x1800070b6  mov     [rsp+68h+cbBuf], eax; cbBuf
0x1800070ba  call    cs:__imp_GetJobA
0x1800070c0  test    eax, eax
0x1800070c2  jnz     short loc_1800070E6
0x1800070c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070cb  cmp     rcx, r14
0x1800070ce  jz      loc_1800071CC
0x1800070d4  test    byte ptr [rcx+1Ch], 8
0x1800070d8  jz      loc_1800071CC
0x1800070de  lea     edx, [rax+23h]
0x1800070e1  jmp     loc_1800071C0
0x1800070e6  mov     rcx, [rbx+60h]; hPrinter
0x1800070ea  lea     rdx, aLpdprinterpass; "LpdPrinterPassThrough"
0x1800070f1  call    IsPrinterDataSet
0x1800070f6  test    eax, eax
0x1800070f8  jz      short loc_180007123
0x1800070fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180007101  cmp     rcx, r14
0x180007104  jz      short loc_180007174
0x180007106  test    byte ptr [rcx+1Ch], 2
0x18000710a  jz      short loc_180007154
0x18000710c  mov     r9, [rbx+58h]
0x180007110  mov     edx, 24h ; '$'
0x180007115  mov     rcx, [rcx+10h]
0x180007119  mov     r8, r12
0x18000711c  call    WPP_SF_s
0x180007121  jmp     short loc_18000714D
0x180007123  mov     rcx, [rbx+60h]; hPrinter
0x180007127  lea     rdx, aLpdprinterdont; "LpdPrinterDontDetect"
0x18000712e  call    IsPrinterDataSet
0x180007133  test    eax, eax
0x180007135  jnz     loc_1800071D3
0x18000713b  mov     edx, esi
0x18000713d  mov     rcx, rbp; Buf
0x180007140  call    IsDataTypeRaw
0x180007145  test    eax, eax
0x180007147  jz      loc_1800071D3
0x18000714d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007154  cmp     rcx, r14
0x180007157  jz      short loc_180007174
0x180007159  test    byte ptr [rcx+1Ch], 2
0x18000715d  jz      short loc_180007174
0x18000715f  mov     r9, [rbx+58h]
0x180007163  mov     edx, 25h ; '%'
0x180007168  mov     rcx, [rcx+10h]
0x18000716c  mov     r8, r12
0x18000716f  call    WPP_SF_s
0x180007174  lea     rax, Str2; "RAW"
0x18000717b  mov     dword ptr [rbx+0BCh], 1
0x180007185  mov     [rdi+30h], rax
0x180007189  mov     r9, rdi; pJob
0x18000718c  mov     edx, [rbx+68h]; JobId
0x18000718f  mov     r8d, 2; Level
0x180007195  mov     rcx, [rbx+60h]; hPrinter
0x180007199  mov     [rsp+68h+cbBuf], 0; Command
0x1800071a1  call    cs:__imp_SetJobA
0x1800071a7  test    eax, eax
0x1800071a9  jnz     short loc_1800071D3
0x1800071ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071b2  cmp     rcx, r14
0x1800071b5  jz      short loc_1800071CC
0x1800071b7  test    byte ptr [rcx+1Ch], 8
0x1800071bb  jz      short loc_1800071CC
0x1800071bd  lea     edx, [rax+26h]
0x1800071c0  mov     rcx, [rcx+10h]
0x1800071c4  mov     r8, r12
0x1800071c7  call    WPP_SF_
0x1800071cc  mov     ebx, 4E26h
0x1800071d1  jmp     short loc_1800071D5
0x1800071d3  xor     ebx, ebx
0x1800071d5  mov     rcx, rdi; hMem
0x1800071d8  call    cs:__imp_LocalFree
0x1800071de  mov     eax, ebx
0x1800071e0  add     rsp, 38h
0x1800071e4  pop     r14
0x1800071e6  pop     r12
0x1800071e8  pop     rdi
0x1800071e9  pop     rsi
0x1800071ea  pop     rbp
0x1800071eb  pop     rbx
0x1800071ec  retn
```
