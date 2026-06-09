# WerpGlobalFlagsForProcess

- ea: `0x18004226c`
- end: `0x180042445`
- name: `WerpGlobalFlagsForProcess`
- size: `473`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800439b0`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x180041da0`
- `0x18004226c`
- `0x18005a9f0`
- `0x1800733c0`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5f0`
- `0x18016f030`

## string_xrefs

- `0x18004238e`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\`

## pseudocode

```c
__int64 __fastcall WerpGlobalFlagsForProcess(HANDLE ProcessHandle)
{
  unsigned int v2; // edi
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned int v6; // esi
  __int128 v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[48]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE ProcessInformation[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v11; // [rsp+78h] [rbp-88h]
  unsigned int v12; // [rsp+2B8h] [rbp+1B8h] BYREF
  HANDLE Handle; // [rsp+2C0h] [rbp+1C0h] BYREF

  Handle = 0;
  memset(v9, 0, 44);
  memset_thunk_772440563353939046(ProcessInformation, 0, 0x220u);
  v12 = 0;
  v2 = 0;
  v8 = 0;
  if ( (NtQueryInformationProcess(ProcessHandle, (PROCESSINFOCLASS)43, ProcessInformation, 0x218u, 0) & 0xC0000000) != 0xC0000000 )
  {
    v3 = WerpPathTail(v11);
    v4 = v3;
    if ( v3 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)(v3 + 2 * v5) );
      v6 = 2 * v5 + 202;
      LOWORD(v8) = 0;
      *((_QWORD *)&v8 + 1) = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v6);
      if ( *((_QWORD *)&v8 + 1) )
      {
        WORD1(v8) = v6;
        if ( (int)RtlAppendUnicodeToString(
                    &v8,
                    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\") >= 0
          && (int)RtlAppendUnicodeToString(&v8, v4) >= 0 )
        {
          *(_DWORD *)v9 = 48;
          *(_QWORD *)&v9[16] = &v8;
          *(_QWORD *)&v9[8] = 0;
          *(_DWORD *)&v9[24] = 64;
          *(_OWORD *)&v9[32] = 0;
          if ( (int)NtOpenKey(&Handle, 1, v9) >= 0 )
          {
            RtlQueryImageFileKeyOption(Handle, L"GlobalFlag", 4, &v12, 4, 0);
            v2 = v12;
          }
        }
      }
    }
  }
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( *((_QWORD *)&v8 + 1) )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, *((_QWORD *)&v8 + 1));
  return v2;
}

```

## disassembly

```asm
0x18004226c  mov     [rsp-8+arg_0], rbx
0x180042271  mov     [rsp-8+arg_18], rsi
0x180042276  push    rbp
0x180042277  push    rdi
0x180042278  push    r14
0x18004227a  lea     rbp, [rsp-190h]
0x180042282  sub     rsp, 290h
0x180042289  xorps   xmm0, xmm0
0x18004228c  mov     rbx, rcx
0x18004228f  movups  [rsp+2A0h+var_250], xmm0
0x180042294  xor     r14d, r14d
0x180042297  lea     rcx, [rsp+2A0h+ProcessInformation]; void *
0x18004229c  xor     eax, eax
0x18004229e  mov     [rbp+1A0h+Handle], r14
0x1800422a5  xor     edx, edx; Val
0x1800422a7  mov     r8d, 220h; Size
0x1800422ad  movups  [rsp+2A0h+var_250+0Ch], xmm0
0x1800422b2  movups  [rsp+2A0h+var_260], xmm0
0x1800422b7  call    memset$thunk$772440563353939046
0x1800422bc  xorps   xmm0, xmm0
0x1800422bf  mov     [rbp+1A0h+arg_8], r14d
0x1800422c6  mov     r9d, 218h; ProcessInformationLength
0x1800422cc  mov     [rsp+2A0h+ReturnLength], r14; ReturnLength
0x1800422d1  lea     r8, [rsp+2A0h+ProcessInformation]; ProcessInformation
0x1800422d6  mov     rcx, rbx; ProcessHandle
0x1800422d9  lea     edx, [r14+2Bh]; ProcessInformationClass
0x1800422dd  mov     edi, r14d
0x1800422e0  movups  [rsp+2A0h+var_270], xmm0
0x1800422e5  call    NtQueryInformationProcess
0x1800422ea  mov     ecx, 0C0000000h
0x1800422ef  and     eax, ecx
0x1800422f1  cmp     eax, ecx
0x1800422f3  jz      short loc_180042343
0x1800422f5  mov     rcx, [rsp+2A0h+var_228]
0x1800422fa  call    WerpPathTail
0x1800422ff  mov     rbx, rax
0x180042302  test    rax, rax
0x180042305  jz      short loc_180042343
0x180042307  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004230b  inc     rcx
0x18004230e  cmp     [rax+rcx*2], r14w
0x180042313  jnz     short loc_18004230B
0x180042315  lea     esi, ds:0CAh[rcx*2]
0x18004231c  mov     word ptr [rsp+2A0h+var_270], r14w
0x180042322  mov     rcx, gs:60h
0x18004232b  xor     edx, edx
0x18004232d  mov     r8d, esi
0x180042330  mov     rcx, [rcx+30h]
0x180042334  call    RtlAllocateHeap_0
0x180042339  mov     qword ptr [rsp+2A0h+var_270+8], rax
0x18004233e  test    rax, rax
0x180042341  jnz     short loc_18004238E
0x180042343  mov     rcx, [rbp+1A0h+Handle]; Handle
0x18004234a  test    rcx, rcx
0x18004234d  jnz     loc_180042434
0x180042353  cmp     qword ptr [rsp+2A0h+var_270+8], r14
0x180042358  jz      short loc_180042373
0x18004235a  mov     rcx, gs:60h
0x180042363  xor     edx, edx
0x180042365  mov     r8, qword ptr [rsp+2A0h+var_270+8]
0x18004236a  mov     rcx, [rcx+30h]
0x18004236e  call    RtlFreeHeap_0
0x180042373  lea     r11, [rsp+2A0h+var_10]
0x18004237b  mov     eax, edi
0x18004237d  mov     rbx, [r11+20h]
0x180042381  mov     rsi, [r11+38h]
0x180042385  mov     rsp, r11
0x180042388  pop     r14
0x18004238a  pop     rdi
0x18004238b  pop     rbp
0x18004238c  retn
0x18004238e  lea     rdx, aRegistryMachin_35; "\\Registry\\Machine\\Software\\Microsof"...
0x180042395  mov     word ptr [rsp+2A0h+var_270+2], si
0x18004239a  lea     rcx, [rsp+2A0h+var_270]
0x18004239f  call    RtlAppendUnicodeToString
0x1800423a4  test    eax, eax
0x1800423a6  js      short loc_180042343
0x1800423a8  mov     rdx, rbx
0x1800423ab  lea     rcx, [rsp+2A0h+var_270]
0x1800423b0  call    RtlAppendUnicodeToString
0x1800423b5  test    eax, eax
0x1800423b7  js      short loc_180042343
0x1800423b9  lea     rax, [rsp+2A0h+var_270]
0x1800423be  mov     dword ptr [rsp+2A0h+var_260], 30h ; '0'
0x1800423c6  xorps   xmm0, xmm0
0x1800423c9  mov     qword ptr [rsp+2A0h+var_250], rax
0x1800423ce  lea     r8, [rsp+2A0h+var_260]
0x1800423d3  mov     qword ptr [rsp+2A0h+var_260+8], r14
0x1800423d8  mov     edx, 1
0x1800423dd  mov     dword ptr [rsp+2A0h+var_250+8], 40h ; '@'
0x1800423e5  lea     rcx, [rbp+1A0h+Handle]
0x1800423ec  movdqu  [rsp+2A0h+var_240], xmm0
0x1800423f2  call    NtOpenKey
0x1800423f7  test    eax, eax
0x1800423f9  js      loc_180042343
0x1800423ff  mov     rcx, [rbp+1A0h+Handle]
0x180042406  lea     r9, [rbp+1A0h+arg_8]
0x18004240d  mov     r8d, 4
0x180042413  mov     [rsp+2A0h+var_278], r14
0x180042418  lea     rdx, aGlobalflag; "GlobalFlag"
0x18004241f  mov     dword ptr [rsp+2A0h+ReturnLength], r8d
0x180042424  call    RtlQueryImageFileKeyOption
0x180042429  mov     edi, [rbp+1A0h+arg_8]
0x18004242f  jmp     loc_180042343
0x180042434  call    NtClose
0x180042439  mov     [rbp+1A0h+Handle], r14
0x180042440  jmp     loc_180042353
```
