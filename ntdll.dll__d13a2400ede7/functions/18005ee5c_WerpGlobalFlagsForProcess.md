# WerpGlobalFlagsForProcess

- ea: `0x18005ee5c`
- end: `0x18005f035`
- name: `WerpGlobalFlagsForProcess`
- size: `473`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800605a0`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18005e988`
- `0x18005ee5c`
- `0x1800773d0`
- `0x1800d4620`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015ee00`
- `0x18016f030`

## string_xrefs

- `0x18005ef7e`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\`

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
0x18005ee5c  mov     [rsp-8+arg_0], rbx
0x18005ee61  mov     [rsp-8+arg_18], rsi
0x18005ee66  push    rbp
0x18005ee67  push    rdi
0x18005ee68  push    r14
0x18005ee6a  lea     rbp, [rsp-190h]
0x18005ee72  sub     rsp, 290h
0x18005ee79  xorps   xmm0, xmm0
0x18005ee7c  mov     rbx, rcx
0x18005ee7f  movups  [rsp+2A0h+var_250], xmm0
0x18005ee84  xor     r14d, r14d
0x18005ee87  lea     rcx, [rsp+2A0h+ProcessInformation]; void *
0x18005ee8c  xor     eax, eax
0x18005ee8e  mov     [rbp+1A0h+Handle], r14
0x18005ee95  xor     edx, edx; Val
0x18005ee97  mov     r8d, 220h; Size
0x18005ee9d  movups  [rsp+2A0h+var_250+0Ch], xmm0
0x18005eea2  movups  [rsp+2A0h+var_260], xmm0
0x18005eea7  call    memset$thunk$772440563353939046
0x18005eeac  xorps   xmm0, xmm0
0x18005eeaf  mov     [rbp+1A0h+arg_8], r14d
0x18005eeb6  mov     r9d, 218h; ProcessInformationLength
0x18005eebc  mov     [rsp+2A0h+ReturnLength], r14; ReturnLength
0x18005eec1  lea     r8, [rsp+2A0h+ProcessInformation]; ProcessInformation
0x18005eec6  mov     rcx, rbx; ProcessHandle
0x18005eec9  lea     edx, [r14+2Bh]; ProcessInformationClass
0x18005eecd  mov     edi, r14d
0x18005eed0  movups  [rsp+2A0h+var_270], xmm0
0x18005eed5  call    NtQueryInformationProcess
0x18005eeda  mov     ecx, 0C0000000h
0x18005eedf  and     eax, ecx
0x18005eee1  cmp     eax, ecx
0x18005eee3  jz      short loc_18005EF33
0x18005eee5  mov     rcx, [rsp+2A0h+var_228]
0x18005eeea  call    WerpPathTail
0x18005eeef  mov     rbx, rax
0x18005eef2  test    rax, rax
0x18005eef5  jz      short loc_18005EF33
0x18005eef7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005eefb  inc     rcx
0x18005eefe  cmp     [rax+rcx*2], r14w
0x18005ef03  jnz     short loc_18005EEFB
0x18005ef05  lea     esi, ds:0CAh[rcx*2]
0x18005ef0c  mov     word ptr [rsp+2A0h+var_270], r14w
0x18005ef12  mov     rcx, gs:60h
0x18005ef1b  xor     edx, edx
0x18005ef1d  mov     r8d, esi
0x18005ef20  mov     rcx, [rcx+30h]
0x18005ef24  call    RtlAllocateHeap_0
0x18005ef29  mov     qword ptr [rsp+2A0h+var_270+8], rax
0x18005ef2e  test    rax, rax
0x18005ef31  jnz     short loc_18005EF7E
0x18005ef33  mov     rcx, [rbp+1A0h+Handle]; Handle
0x18005ef3a  test    rcx, rcx
0x18005ef3d  jnz     loc_18005F024
0x18005ef43  cmp     qword ptr [rsp+2A0h+var_270+8], r14
0x18005ef48  jz      short loc_18005EF63
0x18005ef4a  mov     rcx, gs:60h
0x18005ef53  xor     edx, edx
0x18005ef55  mov     r8, qword ptr [rsp+2A0h+var_270+8]
0x18005ef5a  mov     rcx, [rcx+30h]
0x18005ef5e  call    RtlFreeHeap_0
0x18005ef63  lea     r11, [rsp+2A0h+var_10]
0x18005ef6b  mov     eax, edi
0x18005ef6d  mov     rbx, [r11+20h]
0x18005ef71  mov     rsi, [r11+38h]
0x18005ef75  mov     rsp, r11
0x18005ef78  pop     r14
0x18005ef7a  pop     rdi
0x18005ef7b  pop     rbp
0x18005ef7c  retn
0x18005ef7e  lea     rdx, aRegistryMachin_35; "\\Registry\\Machine\\Software\\Microsof"...
0x18005ef85  mov     word ptr [rsp+2A0h+var_270+2], si
0x18005ef8a  lea     rcx, [rsp+2A0h+var_270]
0x18005ef8f  call    RtlAppendUnicodeToString
0x18005ef94  test    eax, eax
0x18005ef96  js      short loc_18005EF33
0x18005ef98  mov     rdx, rbx
0x18005ef9b  lea     rcx, [rsp+2A0h+var_270]
0x18005efa0  call    RtlAppendUnicodeToString
0x18005efa5  test    eax, eax
0x18005efa7  js      short loc_18005EF33
0x18005efa9  lea     rax, [rsp+2A0h+var_270]
0x18005efae  mov     dword ptr [rsp+2A0h+var_260], 30h ; '0'
0x18005efb6  xorps   xmm0, xmm0
0x18005efb9  mov     qword ptr [rsp+2A0h+var_250], rax
0x18005efbe  lea     r8, [rsp+2A0h+var_260]
0x18005efc3  mov     qword ptr [rsp+2A0h+var_260+8], r14
0x18005efc8  mov     edx, 1
0x18005efcd  mov     dword ptr [rsp+2A0h+var_250+8], 40h ; '@'
0x18005efd5  lea     rcx, [rbp+1A0h+Handle]
0x18005efdc  movdqu  [rsp+2A0h+var_240], xmm0
0x18005efe2  call    NtOpenKey
0x18005efe7  test    eax, eax
0x18005efe9  js      loc_18005EF33
0x18005efef  mov     rcx, [rbp+1A0h+Handle]
0x18005eff6  lea     r9, [rbp+1A0h+arg_8]
0x18005effd  mov     r8d, 4
0x18005f003  mov     [rsp+2A0h+var_278], r14
0x18005f008  lea     rdx, aGlobalflag; "GlobalFlag"
0x18005f00f  mov     dword ptr [rsp+2A0h+ReturnLength], r8d
0x18005f014  call    RtlQueryImageFileKeyOption
0x18005f019  mov     edi, [rbp+1A0h+arg_8]
0x18005f01f  jmp     loc_18005EF33
0x18005f024  call    NtClose
0x18005f029  mov     [rbp+1A0h+Handle], r14
0x18005f030  jmp     loc_18005EF43
```
