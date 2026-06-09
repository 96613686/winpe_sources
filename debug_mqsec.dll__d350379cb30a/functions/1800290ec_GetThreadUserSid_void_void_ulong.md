# _GetThreadUserSid(void *,void * *,ulong *)

- ea: `0x1800290ec`
- end: `0x1800292f0`
- name: `?_GetThreadUserSid@@YAJPEAXPEAPEAXPEAK@Z`
- size: `516`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180028380`
- `0x1800286d0`
- `0x1800287c0`

## callees

- `0x1800049ac`
- `0x18001722c`
- `0x180020680`
- `0x1800290ec`

## import_xrefs

- `msvcrt!free` at `0x1800291f0`
- `msvcrt!free` at `0x180029269`
- `msvcrt!free` at `0x180029287`
- `msvcrt!free` at `0x1800292d4`
- `msvcrt!free` at `0x1800291f0`
- `msvcrt!free` at `0x180029269`
- `msvcrt!free` at `0x180029287`
- `msvcrt!free` at `0x1800292d4`
- `ADVAPI32!CopySid` at `0x18002921c`
- `ADVAPI32!CopySid` at `0x18002921c`
- `ADVAPI32!GetTokenInformation` at `0x180029122`
- `ADVAPI32!GetTokenInformation` at `0x1800291a5`
- `ADVAPI32!GetTokenInformation` at `0x180029122`
- `ADVAPI32!GetTokenInformation` at `0x1800291a5`
- `ADVAPI32!GetLengthSid` at `0x180029202`
- `ADVAPI32!GetLengthSid` at `0x180029202`
- `KERNEL32!GetLastError` at `0x180029128`
- `KERNEL32!GetLastError` at `0x180029133`
- `KERNEL32!GetLastError` at `0x1800291af`
- `KERNEL32!GetLastError` at `0x180029226`
- `KERNEL32!GetLastError` at `0x180029128`
- `KERNEL32!GetLastError` at `0x180029133`
- `KERNEL32!GetLastError` at `0x1800291af`
- `KERNEL32!GetLastError` at `0x180029226`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _GetThreadUserSid(HANDLE TokenHandle, void **a2, unsigned int *a3)
{
  DWORD LastError; // eax
  PSID *v8; // rbx
  DWORD v9; // eax
  PSID v10; // rdi
  unsigned int LengthSid; // ebp
  void *v12; // rax
  DWORD v13; // eax
  signed int v14; // edi
  DWORD TokenInformationLength; // [rsp+78h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, LastError);
    return 3222146091LL;
  }
  v8 = (PSID *)MmAllocate(TokenInformationLength);
  if ( !GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
  {
    v9 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, v9);
    free(v8);
    return 3222146091LL;
  }
  v10 = *v8;
  LengthSid = GetLengthSid(*v8);
  v12 = MmAllocate(LengthSid);
  *a2 = v12;
  if ( CopySid(LengthSid, v12, v10) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
    if ( a3 )
      *a3 = LengthSid;
    free(v8);
    return 0;
  }
  else
  {
    v13 = GetLastError();
    v14 = v13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, v13);
    free(*a2);
    *a2 = 0;
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    free(v8);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x1800290ec  mov     rax, rsp
0x1800290ef  mov     [rax+8], rbx
0x1800290f3  mov     [rax+10h], rbp
0x1800290f7  push    rsi
0x1800290f8  push    rdi
0x1800290f9  push    r14
0x1800290fb  sub     rsp, 40h
0x1800290ff  mov     r14, r8
0x180029102  mov     rsi, rdx
0x180029105  mov     rdi, rcx
0x180029108  mov     dword ptr [rax+20h], 0
0x18002910f  lea     rax, [rax+20h]
0x180029113  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180029118  xor     r9d, r9d; TokenInformationLength
0x18002911b  xor     r8d, r8d; TokenInformation
0x18002911e  lea     edx, [r9+1]; TokenInformationClass
0x180029122  call    cs:__imp_GetTokenInformation
0x180029128  call    cs:__imp_GetLastError
0x18002912e  cmp     eax, 7Ah ; 'z'
0x180029131  jz      short loc_18002917A
0x180029133  call    cs:__imp_GetLastError
0x180029139  lea     rdx, WPP_GLOBAL_Control
0x180029140  mov     rcx, cs:WPP_GLOBAL_Control
0x180029147  cmp     rcx, rdx
0x18002914a  jz      short loc_180029170
0x18002914c  test    byte ptr [rcx+10Ch], 1
0x180029153  jz      short loc_180029170
0x180029155  mov     edx, 0Ah
0x18002915a  mov     r9d, eax
0x18002915d  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180029164  mov     rcx, [rcx+100h]
0x18002916b  call    WPP_SF_d
0x180029170  mov     eax, 0C00E0C2Bh
0x180029175  jmp     loc_1800292DD
0x18002917a  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18002917e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180029183  mov     rbx, rax
0x180029186  mov     [rsp+58h+var_28], rax
0x18002918b  lea     rax, [rsp+58h+TokenInformationLength]
0x180029190  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180029195  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18002919a  mov     r8, rbx; TokenInformation
0x18002919d  mov     edx, 1; TokenInformationClass
0x1800291a2  mov     rcx, rdi; TokenHandle
0x1800291a5  call    cs:__imp_GetTokenInformation
0x1800291ab  test    eax, eax
0x1800291ad  jnz     short loc_1800291FC
0x1800291af  call    cs:__imp_GetLastError
0x1800291b5  lea     rdx, WPP_GLOBAL_Control
0x1800291bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291c3  cmp     rcx, rdx
0x1800291c6  jz      short loc_1800291ED
0x1800291c8  test    byte ptr [rcx+10Ch], 1
0x1800291cf  jz      short loc_1800291ED
0x1800291d1  mov     edx, 0Bh
0x1800291d6  mov     r9d, eax
0x1800291d9  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x1800291e0  mov     rcx, [rcx+100h]
0x1800291e7  call    WPP_SF_d
0x1800291ec  nop
0x1800291ed  mov     rcx, rbx; Block
0x1800291f0  call    cs:__imp_free
0x1800291f6  nop
0x1800291f7  jmp     loc_180029170
0x1800291fc  mov     rdi, [rbx]
0x1800291ff  mov     rcx, rdi; pSid
0x180029202  call    cs:__imp_GetLengthSid
0x180029208  mov     ebp, eax
0x18002920a  mov     ecx, eax; unsigned __int64
0x18002920c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180029211  mov     [rsi], rax
0x180029214  mov     r8, rdi; pSourceSid
0x180029217  mov     rdx, rax; pDestinationSid
0x18002921a  mov     ecx, ebp; nDestinationSidLength
0x18002921c  call    cs:__imp_CopySid
0x180029222  test    eax, eax
0x180029224  jnz     short loc_180029292
0x180029226  call    cs:__imp_GetLastError
0x18002922c  mov     edi, eax
0x18002922e  lea     rdx, WPP_GLOBAL_Control
0x180029235  mov     rcx, cs:WPP_GLOBAL_Control
0x18002923c  cmp     rcx, rdx
0x18002923f  jz      short loc_180029266
0x180029241  test    byte ptr [rcx+10Ch], 1
0x180029248  jz      short loc_180029266
0x18002924a  mov     edx, 0Ch
0x18002924f  mov     r9d, eax
0x180029252  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180029259  mov     rcx, [rcx+100h]
0x180029260  call    WPP_SF_d
0x180029265  nop
0x180029266  mov     rcx, [rsi]; Block
0x180029269  call    cs:__imp_free
0x18002926f  nop
0x180029270  mov     qword ptr [rsi], 0
0x180029277  test    edi, edi
0x180029279  jle     short loc_180029284
0x18002927b  movzx   edi, di
0x18002927e  or      edi, 80070000h
0x180029284  mov     rcx, rbx; Block
0x180029287  call    cs:__imp_free
0x18002928d  nop
0x18002928e  mov     eax, edi
0x180029290  jmp     short loc_1800292DD
0x180029292  lea     rdx, WPP_GLOBAL_Control
0x180029299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292a0  cmp     rcx, rdx
0x1800292a3  jz      short loc_1800292C9
0x1800292a5  test    byte ptr [rcx+10Ch], 4
0x1800292ac  jz      short loc_1800292C9
0x1800292ae  mov     edx, 0Dh
0x1800292b3  mov     r9, [rsi]
0x1800292b6  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x1800292bd  mov     rcx, [rcx+100h]; LoggerHandle
0x1800292c4  call    WPP_SF__sid_
0x1800292c9  test    r14, r14
0x1800292cc  jz      short loc_1800292D1
0x1800292ce  mov     [r14], ebp
0x1800292d1  mov     rcx, rbx; Block
0x1800292d4  call    cs:__imp_free
0x1800292da  nop
0x1800292db  xor     eax, eax
0x1800292dd  mov     rbx, [rsp+58h+arg_0]
0x1800292e2  mov     rbp, [rsp+58h+arg_8]
0x1800292e7  add     rsp, 40h
0x1800292eb  pop     r14
0x1800292ed  pop     rdi
0x1800292ee  pop     rsi
0x1800292ef  retn
```
