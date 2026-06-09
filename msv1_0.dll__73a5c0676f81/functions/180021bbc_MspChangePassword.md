# MspChangePassword

- ea: `0x180021bbc`
- end: `0x180021cdb`
- name: `MspChangePassword`
- size: `287`
- prototype: `__int64 __fastcall(int, int, int, int, int, char, __int64, __int64, DWORD OptionsSupported)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180033148`

## callees

- `0x180021bbc`
- `0x18002e7fc`
- `0x180032500`
- `0x18003536c`
- `0x18006d010`

## import_xrefs

- `netutils!NetRemoteComputerSupports` at `0x180021c9d`
- `netutils!NetRemoteComputerSupports` at `0x180021c9d`

## pseudocode

```c
__int64 __fastcall MspChangePassword(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        char a6,
        __int64 a7,
        PVOID *a8,
        _BYTE *OptionsSupported)
{
  _BYTE *v9; // rsi
  int v14; // ebx
  int v16; // [rsp+20h] [rbp-78h]
  struct _LSA_UNICODE_STRING UncServerName; // [rsp+50h] [rbp-48h] BYREF

  v9 = OptionsSupported;
  *OptionsSupported = 1;
  UncServerName = 0;
  v14 = MspAddBackslashesComputerName(a1, &UncServerName);
  if ( v14 >= 0 )
  {
    v14 = MspChangePasswordSam(&UncServerName, a2, a3, a4, v16, a6, a7, a8, v9);
    if ( v14 == -1073741606 )
    {
      LODWORD(OptionsSupported) = 0;
      if ( !NetRemoteComputerSupports(UncServerName.Buffer, 0x2Cu, (LPDWORD)&OptionsSupported)
        && ((unsigned __int8)OptionsSupported & 8) == 0 )
      {
        v14 -= 31;
      }
    }
    if ( UncServerName.Buffer != *(PWSTR *)(a1 + 8) )
      ((void (*)(void))qword_180088398)();
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids,
      a1,
      v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180021bbc  push    rbx
0x180021bbe  push    rbp
0x180021bbf  push    rsi
0x180021bc0  push    rdi
0x180021bc1  push    r14
0x180021bc3  push    r15
0x180021bc5  sub     rsp, 68h
0x180021bc9  mov     rsi, [rsp+98h+OptionsSupported]
0x180021bd1  mov     r15, rdx
0x180021bd4  xorps   xmm0, xmm0
0x180021bd7  lea     rdx, [rsp+98h+UncServerName]
0x180021bdc  mov     rbp, r9
0x180021bdf  mov     r14, r8
0x180021be2  mov     rdi, rcx
0x180021be5  mov     byte ptr [rsi], 1
0x180021be8  movups  xmmword ptr [rsp+98h+UncServerName.Length], xmm0
0x180021bed  call    MspAddBackslashesComputerName
0x180021bf2  mov     ebx, eax
0x180021bf4  test    eax, eax
0x180021bf6  jns     short loc_180021C3A
0x180021bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bff  lea     rax, WPP_GLOBAL_Control
0x180021c06  cmp     rcx, rax
0x180021c09  jz      loc_180021CCC
0x180021c0f  test    byte ptr [rcx+1Ch], 1
0x180021c13  jz      loc_180021CCC
0x180021c19  mov     rcx, [rcx+10h]
0x180021c1d  lea     r8, WPP_d81ffe40114e3ef115b20edc6117ed6d_Traceguids
0x180021c24  mov     edx, 18h
0x180021c29  mov     [rsp+98h+var_78], ebx
0x180021c2d  mov     r9, rdi
0x180021c30  call    WPP_SF_Zd
0x180021c35  jmp     loc_180021CCC
0x180021c3a  mov     rax, [rsp+98h+arg_38]
0x180021c42  lea     rcx, [rsp+98h+UncServerName]; SystemName
0x180021c47  mov     [rsp+98h+var_58], rsi; __int64
0x180021c4c  mov     r9, rbp
0x180021c4f  mov     [rsp+98h+var_60], rax; __int64
0x180021c54  mov     r8, r14
0x180021c57  mov     rax, [rsp+98h+arg_30]
0x180021c5f  mov     rdx, r15
0x180021c62  mov     [rsp+98h+var_68], rax; __int64
0x180021c67  mov     al, [rsp+98h+arg_28]
0x180021c6e  mov     [rsp+98h+var_70], al; char
0x180021c72  call    MspChangePasswordSam
0x180021c77  mov     ebx, eax
0x180021c79  cmp     eax, 0C00000DAh
0x180021c7e  jnz     short loc_180021CB5
0x180021c80  mov     rcx, [rsp+98h+UncServerName.Buffer]; UncServerName
0x180021c85  lea     r8, [rsp+98h+OptionsSupported]; OptionsSupported
0x180021c8d  mov     edx, 2Ch ; ','; OptionsWanted
0x180021c92  mov     dword ptr [rsp+98h+OptionsSupported], 0
0x180021c9d  call    cs:__imp_NetRemoteComputerSupports
0x180021ca3  test    eax, eax
0x180021ca5  jnz     short loc_180021CB5
0x180021ca7  test    byte ptr [rsp+98h+OptionsSupported], 8
0x180021caf  lea     eax, [rbx-1Fh]
0x180021cb2  cmovz   ebx, eax
0x180021cb5  mov     rcx, [rsp+98h+UncServerName.Buffer]
0x180021cba  cmp     rcx, [rdi+8]
0x180021cbe  jz      short loc_180021CCC
0x180021cc0  mov     rax, cs:qword_180088398
0x180021cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ccc  mov     eax, ebx
0x180021cce  add     rsp, 68h
0x180021cd2  pop     r15
0x180021cd4  pop     r14
0x180021cd6  pop     rdi
0x180021cd7  pop     rsi
0x180021cd8  pop     rbp
0x180021cd9  pop     rbx
0x180021cda  retn
```
