# GetFirstThreadInProcess(ulong,ulong *)

- ea: `0x180047314`
- end: `0x1800474a6`
- name: `?GetFirstThreadInProcess@@YAJKPEAK@Z`
- size: `402`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180047adc`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x180009f00`
- `0x180047314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047437`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004742f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004742f`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180047392`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180047392`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x1800473b8`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x1800473b8`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x1800473d0`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x1800473d0`

## pseudocode

```c
__int64 __fastcall GetFirstThreadInProcess(unsigned int a1, unsigned int *a2)
{
  unsigned int v4; // edi
  char *Toolhelp32Snapshot; // rbx
  DWORD th32OwnerProcessID; // eax
  signed int LastError; // eax
  THREADENTRY32 te; // [rsp+20h] [rbp-38h] BYREF

  memset(&te, 0, sizeof(te));
  if ( !a2 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
    return v4;
  }
  *a2 = 0;
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(4u, 0);
  if ( Toolhelp32Snapshot != (char *)-1LL && Toolhelp32Snapshot + 1 != (char *)1 )
  {
    te.dwSize = 28;
    if ( Thread32First(Toolhelp32Snapshot, &te) )
    {
      if ( te.th32OwnerProcessID == a1 )
        goto LABEL_16;
      while ( Thread32Next(Toolhelp32Snapshot, &te) )
      {
        th32OwnerProcessID = te.th32OwnerProcessID;
        if ( te.th32OwnerProcessID == a1 )
          goto LABEL_12;
      }
    }
    th32OwnerProcessID = te.th32OwnerProcessID;
LABEL_12:
    if ( th32OwnerProcessID != a1 )
    {
      v4 = -2147023728;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, a1);
      goto LABEL_17;
    }
LABEL_16:
    *a2 = te.th32ThreadID;
    v4 = 0;
LABEL_17:
    CloseHandle(Toolhelp32Snapshot);
    return v4;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    v4 = -2147467259;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180047314  mov     [rsp+arg_10], rbx
0x180047319  mov     [rsp+arg_18], rsi
0x18004731e  push    rdi
0x18004731f  sub     rsp, 50h
0x180047323  mov     rax, cs:__security_cookie
0x18004732a  xor     rax, rsp
0x18004732d  mov     [rsp+58h+var_18], rax
0x180047332  xorps   xmm0, xmm0
0x180047335  xor     eax, eax
0x180047337  mov     rdi, rdx
0x18004733a  mov     esi, ecx
0x18004733c  movups  xmmword ptr [rsp+58h+te.dwSize], xmm0
0x180047341  movups  xmmword ptr [rsp+58h+te.th32OwnerProcessID], xmm0
0x180047346  test    rdx, rdx
0x180047349  jnz     short loc_18004738B
0x18004734b  mov     edi, 80070057h
0x180047350  mov     rcx, cs:WPP_GLOBAL_Control
0x180047357  lea     rax, WPP_GLOBAL_Control
0x18004735e  cmp     rcx, rax
0x180047361  jz      loc_180047487
0x180047367  test    byte ptr [rcx+1Ch], 1
0x18004736b  jz      loc_180047487
0x180047371  mov     rcx, [rcx+10h]
0x180047375  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x18004737c  mov     edx, 0Dh
0x180047381  call    WPP_SF_
0x180047386  jmp     loc_180047487
0x18004738b  mov     [rdx], eax
0x18004738d  xor     edx, edx; th32ProcessID
0x18004738f  lea     ecx, [rdx+4]; dwFlags
0x180047392  call    cs:__imp_CreateToolhelp32Snapshot
0x180047398  mov     rbx, rax
0x18004739b  inc     rax
0x18004739e  cmp     rax, 1
0x1800473a2  jbe     loc_180047437
0x1800473a8  lea     rdx, [rsp+58h+te]; lpte
0x1800473ad  mov     [rsp+58h+te.dwSize], 1Ch
0x1800473b5  mov     rcx, rbx; hSnapshot
0x1800473b8  call    cs:__imp_Thread32First
0x1800473be  test    eax, eax
0x1800473c0  jz      short loc_1800473E4
0x1800473c2  cmp     [rsp+58h+te.th32OwnerProcessID], esi
0x1800473c6  jz      short loc_180047424
0x1800473c8  lea     rdx, [rsp+58h+te]; lpte
0x1800473cd  mov     rcx, rbx; hSnapshot
0x1800473d0  call    cs:__imp_Thread32Next
0x1800473d6  test    eax, eax
0x1800473d8  jz      short loc_1800473E4
0x1800473da  mov     eax, [rsp+58h+te.th32OwnerProcessID]
0x1800473de  cmp     eax, esi
0x1800473e0  jnz     short loc_1800473C8
0x1800473e2  jmp     short loc_1800473E8
0x1800473e4  mov     eax, [rsp+58h+te.th32OwnerProcessID]
0x1800473e8  cmp     eax, esi
0x1800473ea  jz      short loc_180047424
0x1800473ec  mov     edi, 80070490h
0x1800473f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473f8  lea     rax, WPP_GLOBAL_Control
0x1800473ff  cmp     rcx, rax
0x180047402  jz      short loc_18004742C
0x180047404  test    byte ptr [rcx+1Ch], 1
0x180047408  jz      short loc_18004742C
0x18004740a  mov     rcx, [rcx+10h]
0x18004740e  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x180047415  mov     edx, 0Fh
0x18004741a  mov     r9d, esi
0x18004741d  call    WPP_SF_d
0x180047422  jmp     short loc_18004742C
0x180047424  mov     eax, [rsp+58h+te.th32ThreadID]
0x180047428  mov     [rdi], eax
0x18004742a  xor     edi, edi
0x18004742c  mov     rcx, rbx; hObject
0x18004742f  call    cs:__imp_CloseHandle
0x180047435  jmp     short loc_180047487
0x180047437  call    cs:__imp_GetLastError
0x18004743d  mov     edi, eax
0x18004743f  test    eax, eax
0x180047441  jle     short loc_18004744C
0x180047443  movzx   edi, ax
0x180047446  or      edi, 80070000h
0x18004744c  test    edi, edi
0x18004744e  mov     eax, 80004005h
0x180047453  cmovns  edi, eax
0x180047456  mov     rcx, cs:WPP_GLOBAL_Control
0x18004745d  lea     rax, WPP_GLOBAL_Control
0x180047464  cmp     rcx, rax
0x180047467  jz      short loc_180047487
0x180047469  test    byte ptr [rcx+1Ch], 1
0x18004746d  jz      short loc_180047487
0x18004746f  mov     rcx, [rcx+10h]
0x180047473  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x18004747a  mov     edx, 0Eh
0x18004747f  mov     r9d, edi
0x180047482  call    WPP_SF_d
0x180047487  mov     eax, edi
0x180047489  mov     rcx, [rsp+58h+var_18]
0x18004748e  xor     rcx, rsp; StackCookie
0x180047491  call    __security_check_cookie
0x180047496  mov     rbx, [rsp+58h+arg_10]
0x18004749b  mov     rsi, [rsp+58h+arg_18]
0x1800474a0  add     rsp, 50h
0x1800474a4  pop     rdi
0x1800474a5  retn
```
