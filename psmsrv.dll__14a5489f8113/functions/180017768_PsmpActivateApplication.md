# PsmpActivateApplication

- ea: `0x180017768`
- end: `0x180017882`
- name: `PsmpActivateApplication`
- size: `282`
- prototype: `__int64 __fastcall(char, PSID Sid2, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180019df0`

## callees

- `0x180008cc0`
- `0x180009b40`
- `0x1800114d0`
- `0x180017768`
- `0x18001eb88`
- `0x18001ee1c`

## pseudocode

```c
__int64 __fastcall PsmpActivateApplication(char a1, PSID Sid2, __int64 a3)
{
  __int64 v4; // r9
  int ApplicationByManagerForUser; // eax
  unsigned int v8; // ebx
  __int64 v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a3 + 2 * v4) );
  ApplicationByManagerForUser = PsmpFindApplicationByManagerForUser(Sid2, a1, a3, 2 * v4 + 2, 0, &v12);
  v8 = ApplicationByManagerForUser;
  if ( ApplicationByManagerForUser >= 0 )
  {
    v10 = v12;
    if ( *(_QWORD *)(v12 + 192) )
    {
      PsmpChangeApplicationState(
        v12,
        0,
        (__int64 (__fastcall *)(__int64, __int64, unsigned int *, __int64 *))PsmpExitBackgroundState,
        0xBu,
        1,
        0);
      v11 = 0;
    }
    else
    {
      v11 = -1073741637;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_iS_sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), a3, Sid2, 187);
    }
    PsmpDereferenceApplicationEx(v10, 0);
    return v11;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S_sid_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), Sid2, a1, ApplicationByManagerForUser);
    return v8;
  }
}

```

## disassembly

```asm
0x180017768  mov     [rsp+arg_0], rbx
0x18001776d  mov     [rsp+arg_8], rbp
0x180017772  push    rsi
0x180017773  push    rdi
0x180017774  push    r14
0x180017776  sub     rsp, 40h
0x18001777a  xor     r14d, r14d
0x18001777d  mov     rsi, r8
0x180017780  mov     [rsp+58h+arg_18], r14
0x180017785  or      r9, 0FFFFFFFFFFFFFFFFh
0x180017789  mov     rbp, rdx
0x18001778c  mov     edi, ecx
0x18001778e  inc     r9
0x180017791  cmp     [r8+r9*2], r14w
0x180017796  jnz     short loc_18001778E
0x180017798  lea     rax, [rsp+58h+arg_18]
0x18001779d  mov     edx, edi
0x18001779f  mov     [rsp+58h+var_30], rax; __int64
0x1800177a4  lea     r9, ds:2[r9*2]
0x1800177ac  mov     rcx, rbp; Sid2
0x1800177af  mov     dword ptr [rsp+58h+pSid], r14d; int
0x1800177b4  call    PsmpFindApplicationByManagerForUser
0x1800177b9  mov     ebx, eax
0x1800177bb  test    eax, eax
0x1800177bd  jns     short loc_1800177F4
0x1800177bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177c6  test    byte ptr [rcx+1Ch], 2
0x1800177ca  jz      short loc_1800177F0
0x1800177cc  cmp     byte ptr [rcx+19h], 2
0x1800177d0  jb      short loc_1800177F0
0x1800177d2  mov     rcx, [rcx+10h]; LoggerHandle
0x1800177d6  mov     edx, 0Ah
0x1800177db  mov     dword ptr [rsp+58h+var_28], eax; char
0x1800177df  mov     r9, rsi
0x1800177e2  mov     dword ptr [rsp+58h+var_30], edi; char
0x1800177e6  mov     [rsp+58h+pSid], rbp; pSid
0x1800177eb  call    WPP_SF_S_sid_dd
0x1800177f0  mov     eax, ebx
0x1800177f2  jmp     short loc_18001786F
0x1800177f4  mov     rbx, [rsp+58h+arg_18]
0x1800177f9  cmp     [rbx+0C0h], r14
0x180017800  jnz     short loc_18001783C
0x180017802  mov     edi, 0C00000BBh
0x180017807  mov     rcx, cs:WPP_GLOBAL_Control
0x18001780e  test    byte ptr [rcx+1Ch], 2
0x180017812  jz      short loc_180017863
0x180017814  cmp     byte ptr [rcx+19h], 2
0x180017818  jb      short loc_180017863
0x18001781a  mov     r9, [rbx+60h]
0x18001781e  mov     edx, 0Bh
0x180017823  mov     rcx, [rcx+10h]; LoggerHandle
0x180017827  mov     dword ptr [rsp+58h+var_28], edi; char
0x18001782b  mov     [rsp+58h+var_30], rbp; pSid
0x180017830  mov     [rsp+58h+pSid], rsi; __int64
0x180017835  call    WPP_SF_iS_sid_d
0x18001783a  jmp     short loc_180017863
0x18001783c  mov     [rsp+58h+var_30], r14
0x180017841  lea     r8, PsmpExitBackgroundState
0x180017848  mov     r9d, 0Bh
0x18001784e  mov     dword ptr [rsp+58h+pSid], 1
0x180017856  xor     edx, edx
0x180017858  mov     rcx, rbx
0x18001785b  call    PsmpChangeApplicationState
0x180017860  mov     edi, r14d
0x180017863  xor     edx, edx
0x180017865  mov     rcx, rbx
0x180017868  call    PsmpDereferenceApplicationEx
0x18001786d  mov     eax, edi
0x18001786f  mov     rbx, [rsp+58h+arg_0]
0x180017874  mov     rbp, [rsp+58h+arg_8]
0x180017879  add     rsp, 40h
0x18001787d  pop     r14
0x18001787f  pop     rdi
0x180017880  pop     rsi
0x180017881  retn
```
