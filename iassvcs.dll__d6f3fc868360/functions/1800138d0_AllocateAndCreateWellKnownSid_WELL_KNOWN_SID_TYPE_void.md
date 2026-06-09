# AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x1800138d0`
- end: `0x180013b25`
- name: `?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `597`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180013b2c`
- `0x180014128`

## callees

- `0x1800138d0`
- `0x180014ba8`
- `0x180014c58`
- `0x180017754`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x18001390d`
- `ADVAPI32!CreateWellKnownSid` at `0x180013a6c`
- `ADVAPI32!CreateWellKnownSid` at `0x18001390d`
- `ADVAPI32!CreateWellKnownSid` at `0x180013a6c`
- `KERNEL32!GlobalFree` at `0x180013af9`
- `KERNEL32!GlobalFree` at `0x180013af9`
- `KERNEL32!GlobalAlloc` at `0x1800139f9`
- `KERNEL32!GlobalAlloc` at `0x1800139f9`
- `KERNEL32!GetLastError` at `0x18001396f`
- `KERNEL32!GetLastError` at `0x180013a7a`
- `KERNEL32!GetLastError` at `0x18001396f`
- `KERNEL32!GetLastError` at `0x180013a7a`

## string_xrefs

- `0x180013936`: `Creating a sid worked with no memory allocated for it.( This is not good )`
- `0x1800139b4`: `Getting the SID length failed, can't create the sid (Type = %d), error = %x`
- `0x180013aba`: `Creating SID failed ( SidType = %d ), Error %x`

## pseudocode

```c
__int64 __fastcall AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, void **a2)
{
  DWORD LastError; // ebx
  HGLOBAL v6; // rax
  void *v7; // rbp
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || *a2 )
    return 87;
  LODWORD(dwBytes) = 0;
  if ( CreateWellKnownSid(WellKnownSidType, 0, 0, (DWORD *)&dwBytes) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("Creating a sid worked with no memory allocated for it.( This is not good )");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids, "NAPBASE");
    }
    return 13;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("Getting the SID length failed, can't create the sid (Type = %d), error = %x");
      WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18);
    }
    return LastError;
  }
  v6 = GlobalAlloc(0, (unsigned int)dwBytes);
  v7 = v6;
  if ( v6 )
  {
    LastError = 0;
    if ( CreateWellKnownSid(WellKnownSidType, 0, v6, (DWORD *)&dwBytes) )
      goto LABEL_28;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("Creating SID failed ( SidType = %d ), Error %x");
      WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20);
    }
    if ( !LastError )
LABEL_28:
      *a2 = v7;
    else
      GlobalFree(v7);
    return LastError;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WppDbgPrint("GlobalAlloc failed. Out of memory");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids, "NAPBASE");
  }
  return 8;
}

```

## disassembly

```asm
0x1800138d0  mov     rax, rsp
0x1800138d3  mov     [rax+8], rbx
0x1800138d7  mov     [rax+18h], rbp
0x1800138db  push    rdi
0x1800138dc  push    r14
0x1800138de  push    r15
0x1800138e0  sub     rsp, 30h
0x1800138e4  mov     r15, rdx
0x1800138e7  mov     r14d, ecx
0x1800138ea  test    rdx, rdx
0x1800138ed  jz      loc_180013B0C
0x1800138f3  cmp     qword ptr [rdx], 0
0x1800138f7  jnz     loc_180013B0C
0x1800138fd  lea     r9, [rax+10h]; cbSid
0x180013901  mov     dword ptr [rax+10h], 0
0x180013908  xor     r8d, r8d; pSid
0x18001390b  xor     edx, edx; DomainSid
0x18001390d  call    cs:__imp_CreateWellKnownSid
0x180013913  test    eax, eax
0x180013915  jz      short loc_18001396F
0x180013917  mov     rcx, cs:WPP_GLOBAL_Control
0x18001391e  lea     rax, WPP_GLOBAL_Control
0x180013925  cmp     rcx, rax
0x180013928  jz      short loc_180013965
0x18001392a  cmp     byte ptr [rcx+19h], 2
0x18001392e  jb      short loc_180013965
0x180013930  test    byte ptr [rcx+1Ch], 1
0x180013934  jz      short loc_180013965
0x180013936  lea     rcx, aCreatingASidWo; "Creating a sid worked with no memory al"...
0x18001393d  call    WppDbgPrint
0x180013942  mov     rcx, cs:WPP_GLOBAL_Control
0x180013949  lea     r9, aNapbase; "NAPBASE"
0x180013950  mov     edx, 11h
0x180013955  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18001395c  mov     rcx, [rcx+10h]
0x180013960  call    WPP_SF_s
0x180013965  mov     eax, 0Dh
0x18001396a  jmp     loc_180013B11
0x18001396f  call    cs:__imp_GetLastError
0x180013975  mov     ebx, eax
0x180013977  cmp     eax, 7Ah ; 'z'
0x18001397a  jz      short loc_1800139F3
0x18001397c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013983  lea     rax, WPP_GLOBAL_Control
0x18001398a  cmp     rcx, rax
0x18001398d  jz      short loc_1800139EC
0x18001398f  cmp     byte ptr [rcx+19h], 2
0x180013993  jb      short loc_1800139EC
0x180013995  test    byte ptr [rcx+1Ch], 1
0x180013999  jz      short loc_1800139EC
0x18001399b  movzx   edi, bx
0x18001399e  test    ebx, ebx
0x1800139a0  jg      short loc_1800139A7
0x1800139a2  mov     r8d, ebx
0x1800139a5  jmp     short loc_1800139B1
0x1800139a7  mov     r8d, edi
0x1800139aa  or      r8d, 80070000h
0x1800139b1  mov     edx, r14d
0x1800139b4  lea     rcx, aGettingTheSidL; "Getting the SID length failed, can't cr"...
0x1800139bb  call    WppDbgPrint
0x1800139c0  test    ebx, ebx
0x1800139c2  jg      short loc_1800139C8
0x1800139c4  mov     edi, ebx
0x1800139c6  jmp     short loc_1800139CE
0x1800139c8  or      edi, 80070000h
0x1800139ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139d5  mov     edx, 12h
0x1800139da  mov     [rsp+48h+var_20], edi
0x1800139de  mov     [rsp+48h+var_28], r14d
0x1800139e3  mov     rcx, [rcx+10h]
0x1800139e7  call    WPP_SF_sdD
0x1800139ec  mov     eax, ebx
0x1800139ee  jmp     loc_180013B11
0x1800139f3  mov     edx, dword ptr [rsp+48h+dwBytes]; dwBytes
0x1800139f7  xor     ecx, ecx; uFlags
0x1800139f9  call    cs:__imp_GlobalAlloc
0x1800139ff  mov     rbp, rax
0x180013a02  test    rax, rax
0x180013a05  jnz     short loc_180013A5D
0x180013a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a0e  lea     rax, WPP_GLOBAL_Control
0x180013a15  cmp     rcx, rax
0x180013a18  jz      short loc_180013A53
0x180013a1a  cmp     byte ptr [rcx+19h], 2
0x180013a1e  jb      short loc_180013A53
0x180013a20  test    byte ptr [rcx+1Ch], 1
0x180013a24  jz      short loc_180013A53
0x180013a26  lea     rcx, aGlobalallocFai; "GlobalAlloc failed. Out of memory"
0x180013a2d  call    WppDbgPrint
0x180013a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a39  lea     edx, [rbp+13h]
0x180013a3c  lea     r9, aNapbase; "NAPBASE"
0x180013a43  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180013a4a  mov     rcx, [rcx+10h]
0x180013a4e  call    WPP_SF_s
0x180013a53  mov     eax, 8
0x180013a58  jmp     loc_180013B11
0x180013a5d  lea     r9, [rsp+48h+dwBytes]; cbSid
0x180013a62  mov     r8, rbp; pSid
0x180013a65  xor     edx, edx; DomainSid
0x180013a67  mov     ecx, r14d; WellKnownSidType
0x180013a6a  xor     ebx, ebx
0x180013a6c  call    cs:__imp_CreateWellKnownSid
0x180013a72  test    eax, eax
0x180013a74  jnz     loc_180013B04
0x180013a7a  call    cs:__imp_GetLastError
0x180013a80  mov     ebx, eax
0x180013a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a89  lea     rax, WPP_GLOBAL_Control
0x180013a90  cmp     rcx, rax
0x180013a93  jz      short loc_180013AF2
0x180013a95  cmp     byte ptr [rcx+19h], 2
0x180013a99  jb      short loc_180013AF2
0x180013a9b  test    byte ptr [rcx+1Ch], 1
0x180013a9f  jz      short loc_180013AF2
0x180013aa1  movzx   edi, bx
0x180013aa4  test    ebx, ebx
0x180013aa6  jg      short loc_180013AAD
0x180013aa8  mov     r8d, ebx
0x180013aab  jmp     short loc_180013AB7
0x180013aad  mov     r8d, edi
0x180013ab0  or      r8d, 80070000h
0x180013ab7  mov     edx, r14d
0x180013aba  lea     rcx, aCreatingSidFai; "Creating SID failed ( SidType = %d ), E"...
0x180013ac1  call    WppDbgPrint
0x180013ac6  test    ebx, ebx
0x180013ac8  jg      short loc_180013ACE
0x180013aca  mov     edi, ebx
0x180013acc  jmp     short loc_180013AD4
0x180013ace  or      edi, 80070000h
0x180013ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013adb  mov     edx, 14h
0x180013ae0  mov     [rsp+48h+var_20], edi
0x180013ae4  mov     [rsp+48h+var_28], r14d
0x180013ae9  mov     rcx, [rcx+10h]
0x180013aed  call    WPP_SF_sdD
0x180013af2  test    ebx, ebx
0x180013af4  jz      short loc_180013B04
0x180013af6  mov     rcx, rbp; hMem
0x180013af9  call    cs:__imp_GlobalFree
0x180013aff  jmp     loc_1800139EC
0x180013b04  mov     [r15], rbp
0x180013b07  jmp     loc_1800139EC
0x180013b0c  mov     eax, 57h ; 'W'
0x180013b11  mov     rbx, [rsp+48h+arg_0]
0x180013b16  mov     rbp, [rsp+48h+arg_10]
0x180013b1b  add     rsp, 30h
0x180013b1f  pop     r15
0x180013b21  pop     r14
0x180013b23  pop     rdi
0x180013b24  retn
```
