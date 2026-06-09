# CMDCOM::ComMDRestoreWithPasswdW(ushort const *,ulong,ulong,ushort const *)

- ea: `0x180019aa0`
- end: `0x180019b53`
- name: `?ComMDRestoreWithPasswdW@CMDCOM@@UEAAJPEBGKK0@Z`
- size: `179`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this, char *, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180019454`
- `0x180019aa0`
- `0x1800309d0`

## import_xrefs

- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180019ae7`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180019ae7`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180019afd`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180019afd`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180019ad9`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180019ad9`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180019b2d`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180019b2d`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDRestoreWithPasswdW(
        CMDCOM *this,
        char *a2,
        unsigned int a3,
        int a4,
        const unsigned __int16 *a5)
{
  unsigned int v9; // ebx
  char *StrA; // rax
  _BYTE v12[128]; // [rsp+40h] [rbp-B8h] BYREF

  STRAU::STRAU((STRAU *)v12);
  if ( STRAU::Copy((STRAU *)v12, a5) )
  {
    StrA = STRAU::QueryStrA((STRAU *)v12);
    v9 = CMDCOM::ComMDRestoreD(this, a2, a3, a4, 1, StrA, 1);
  }
  else
  {
    v9 = -2147024882;
  }
  STRAU::~STRAU((STRAU *)v12);
  return v9;
}

```

## disassembly

```asm
0x180019aa0  push    rbx
0x180019aa2  push    rbp
0x180019aa3  push    rsi
0x180019aa4  push    rdi
0x180019aa5  push    r14
0x180019aa7  sub     rsp, 0D0h
0x180019aae  mov     rax, cs:__security_cookie
0x180019ab5  xor     rax, rsp
0x180019ab8  mov     [rsp+0F8h+var_38], rax
0x180019ac0  mov     rbx, [rsp+0F8h+arg_20]
0x180019ac8  mov     rsi, rcx
0x180019acb  lea     rcx, [rsp+0F8h+var_B8]
0x180019ad0  mov     edi, r9d
0x180019ad3  mov     r14d, r8d
0x180019ad6  mov     rbp, rdx
0x180019ad9  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180019adf  mov     rdx, rbx
0x180019ae2  lea     rcx, [rsp+0F8h+var_B8]
0x180019ae7  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x180019aed  test    eax, eax
0x180019aef  jnz     short loc_180019AF8
0x180019af1  mov     ebx, 8007000Eh
0x180019af6  jmp     short loc_180019B28
0x180019af8  lea     rcx, [rsp+0F8h+var_B8]
0x180019afd  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x180019b03  mov     ecx, 1
0x180019b08  mov     r9d, edi; unsigned int
0x180019b0b  mov     [rsp+0F8h+var_C8], ecx; int
0x180019b0f  mov     r8d, r14d; unsigned int
0x180019b12  mov     [rsp+0F8h+var_D0], rax; char *
0x180019b17  mov     rdx, rbp; char *
0x180019b1a  mov     [rsp+0F8h+var_D8], ecx; int
0x180019b1e  mov     rcx, rsi; this
0x180019b21  call    ?ComMDRestoreD@CMDCOM@@QEAAJPEADKKH0H@Z; CMDCOM::ComMDRestoreD(char *,ulong,ulong,int,char *,int)
0x180019b26  mov     ebx, eax
0x180019b28  lea     rcx, [rsp+0F8h+var_B8]
0x180019b2d  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180019b33  mov     eax, ebx
0x180019b35  mov     rcx, [rsp+0F8h+var_38]
0x180019b3d  xor     rcx, rsp; StackCookie
0x180019b40  call    __security_check_cookie
0x180019b45  add     rsp, 0D0h
0x180019b4c  pop     r14
0x180019b4e  pop     rdi
0x180019b4f  pop     rsi
0x180019b50  pop     rbp
0x180019b51  pop     rbx
0x180019b52  retn
```
