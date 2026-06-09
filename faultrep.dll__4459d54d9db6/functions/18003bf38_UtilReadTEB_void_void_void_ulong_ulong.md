# UtilReadTEB(void *,void *,void *,ulong,ulong)

- ea: `0x18003bf38`
- end: `0x18003c084`
- name: `?UtilReadTEB@@YAJPEAX00KK@Z`
- size: `332`
- prototype: `__int64 __fastcall(HANDLE hProcess, HANDLE ThreadHandle, void *lpBuffer, unsigned int, unsigned int nSize)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014c34`
- `0x180028ea0`

## callees

- `0x180009ed8`
- `0x18003bf38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c021`
- `ntdll!NtQueryInformationThread` at `0x18003bf8a`
- `ntdll!NtQueryInformationThread` at `0x18003bf8a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003bfe9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003bfe9`

## pseudocode

```c
__int64 __fastcall UtilReadTEB(
        HANDLE hProcess,
        HANDLE ThreadHandle,
        void *lpBuffer,
        unsigned int a4,
        unsigned int nSize)
{
  __int64 v5; // rsi
  NTSTATUS InformationThread; // ebx
  signed int v9; // ebx
  signed int LastError; // eax
  _OWORD ThreadInformation[5]; // [rsp+30h] [rbp-58h] BYREF

  v5 = a4;
  memset(ThreadInformation, 0, 48);
  if ( ThreadHandle && lpBuffer )
  {
    InformationThread = NtQueryInformationThread(ThreadHandle, ThreadBasicInformation, ThreadInformation, 0x30u, 0);
    if ( InformationThread >= 0 )
    {
      if ( ReadProcessMemory(hProcess, (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + v5), lpBuffer, nSize, 0) )
      {
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 >= 0 )
          return (unsigned int)-2147467259;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
      return (unsigned int)(InformationThread | 0x10000000);
    }
    return (unsigned int)v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18003bf38  push    rbx
0x18003bf3a  push    rbp
0x18003bf3b  push    rsi
0x18003bf3c  push    rdi
0x18003bf3d  sub     rsp, 68h
0x18003bf41  mov     esi, r9d
0x18003bf44  xorps   xmm0, xmm0
0x18003bf47  mov     rdi, r8
0x18003bf4a  mov     rax, rdx
0x18003bf4d  mov     rbp, rcx
0x18003bf50  movups  [rsp+88h+ThreadInformation], xmm0
0x18003bf55  movups  [rsp+88h+var_48], xmm0
0x18003bf5a  movups  [rsp+88h+var_38], xmm0
0x18003bf5f  test    rdx, rdx
0x18003bf62  jz      loc_18003C048
0x18003bf68  test    r8, r8
0x18003bf6b  jz      loc_18003C048
0x18003bf71  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18003bf77  mov     [rsp+88h+ReturnLength], 0; ReturnLength
0x18003bf80  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x18003bf85  xor     edx, edx; ThreadInformationClass
0x18003bf87  mov     rcx, rax; ThreadHandle
0x18003bf8a  call    cs:__imp_NtQueryInformationThread
0x18003bf90  mov     ebx, eax
0x18003bf92  test    eax, eax
0x18003bf94  jns     short loc_18003BFCA
0x18003bf96  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf9d  lea     rax, WPP_GLOBAL_Control
0x18003bfa4  cmp     rcx, rax
0x18003bfa7  jz      short loc_18003BFC4
0x18003bfa9  test    byte ptr [rcx+1Ch], 1
0x18003bfad  jz      short loc_18003BFC4
0x18003bfaf  mov     rcx, [rcx+10h]
0x18003bfb3  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003bfba  mov     edx, 37h ; '7'
0x18003bfbf  call    WPP_SF_
0x18003bfc4  bts     ebx, 1Ch
0x18003bfc8  jmp     short loc_18003C044
0x18003bfca  mov     r9d, dword ptr [rsp+88h+nSize]; nSize
0x18003bfd2  mov     rdx, rsi
0x18003bfd5  add     rdx, qword ptr [rsp+88h+ThreadInformation+8]; lpBaseAddress
0x18003bfda  mov     r8, rdi; lpBuffer
0x18003bfdd  mov     rcx, rbp; hProcess
0x18003bfe0  mov     [rsp+88h+ReturnLength], 0; lpNumberOfBytesRead
0x18003bfe9  call    cs:__imp_ReadProcessMemory
0x18003bfef  test    eax, eax
0x18003bff1  jnz     short loc_18003C042
0x18003bff3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bffa  lea     rax, WPP_GLOBAL_Control
0x18003c001  cmp     rcx, rax
0x18003c004  jz      short loc_18003C021
0x18003c006  test    byte ptr [rcx+1Ch], 1
0x18003c00a  jz      short loc_18003C021
0x18003c00c  mov     rcx, [rcx+10h]
0x18003c010  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003c017  mov     edx, 38h ; '8'
0x18003c01c  call    WPP_SF_
0x18003c021  call    cs:__imp_GetLastError
0x18003c027  mov     ebx, eax
0x18003c029  test    eax, eax
0x18003c02b  jle     short loc_18003C036
0x18003c02d  movzx   ebx, ax
0x18003c030  or      ebx, 80070000h
0x18003c036  test    ebx, ebx
0x18003c038  mov     eax, 80004005h
0x18003c03d  cmovns  ebx, eax
0x18003c040  jmp     short loc_18003C044
0x18003c042  xor     ebx, ebx
0x18003c044  mov     eax, ebx
0x18003c046  jmp     short loc_18003C07B
0x18003c048  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c04f  lea     rax, WPP_GLOBAL_Control
0x18003c056  cmp     rcx, rax
0x18003c059  jz      short loc_18003C076
0x18003c05b  test    byte ptr [rcx+1Ch], 1
0x18003c05f  jz      short loc_18003C076
0x18003c061  mov     rcx, [rcx+10h]
0x18003c065  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003c06c  mov     edx, 36h ; '6'
0x18003c071  call    WPP_SF_
0x18003c076  mov     eax, 80070057h
0x18003c07b  add     rsp, 68h
0x18003c07f  pop     rdi
0x18003c080  pop     rsi
0x18003c081  pop     rbp
0x18003c082  pop     rbx
0x18003c083  retn
```
