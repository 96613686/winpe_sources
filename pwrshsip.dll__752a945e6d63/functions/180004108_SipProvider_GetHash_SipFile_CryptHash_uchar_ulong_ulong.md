# SipProvider::GetHash(SipFile *,CryptHash *,uchar *,ulong,ulong *)

- ea: `0x180004108`
- end: `0x180004217`
- name: `?GetHash@SipProvider@@QEAAKPEAVSipFile@@PEAVCryptHash@@PEAEKPEAK@Z`
- size: `271`
- prototype: `unsigned int(SipProvider *__hidden this, struct SipFile *, struct CryptHash *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004220`
- `0x1800050b0`

## callees

- `0x18000409c`
- `0x180004108`
- `0x1800054f0`
- `0x180006010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800041c4`
- `KERNEL32!GetLastError` at `0x1800041c4`
- `ADVAPI32!CryptHashData` at `0x1800041ba`
- `ADVAPI32!CryptHashData` at `0x1800041ba`

## pseudocode

```c
__int64 __fastcall SipProvider::GetHash(
        SipProvider *this,
        struct SipFile *a2,
        HCRYPTHASH *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int *a6)
{
  DWORD LastError; // ebx
  DWORD v10; // eax
  DWORD dwDataLen[4]; // [rsp+30h] [rbp-448h] BYREF
  BYTE pbData[1024]; // [rsp+40h] [rbp-438h] BYREF

  dwDataLen[0] = 0;
  if ( a2 && a3 && a4 && a6 )
  {
    *a4 = 0;
    *a6 = 0;
    LastError = (*(__int64 (__fastcall **)(struct SipFile *))(*(_QWORD *)a2 + 16LL))(a2);
    if ( !LastError )
    {
      while ( 1 )
      {
        v10 = (*(__int64 (__fastcall **)(struct SipFile *, __int64, BYTE *, DWORD *))(*(_QWORD *)a2 + 8LL))(
                a2,
                1024,
                pbData,
                dwDataLen);
        LastError = v10;
        if ( v10 )
          break;
        if ( !CryptHashData(*a3, pbData, dwDataLen[0], 0) )
          LastError = GetLastError();
        if ( LastError )
          return LastError;
      }
      if ( v10 == 259 )
        return CryptHash::GetHash((CryptHash *)a3, a4, 0x400u, a6);
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x180004108  push    rbx
0x18000410a  push    rsi
0x18000410b  push    rdi
0x18000410c  push    r14
0x18000410e  push    r15
0x180004110  sub     rsp, 450h
0x180004117  mov     rax, cs:__security_cookie
0x18000411e  xor     rax, rsp
0x180004121  mov     [rsp+478h+var_38], rax
0x180004129  mov     r14, [rsp+478h+arg_28]
0x180004131  mov     rsi, r9
0x180004134  mov     [rsp+478h+dwDataLen], 0
0x18000413c  mov     r15, r8
0x18000413f  mov     rdi, rdx
0x180004142  test    rdx, rdx
0x180004145  jz      loc_1800041F1
0x18000414b  test    r8, r8
0x18000414e  jz      loc_1800041F1
0x180004154  test    r9, r9
0x180004157  jz      loc_1800041F1
0x18000415d  test    r14, r14
0x180004160  jz      loc_1800041F1
0x180004166  mov     byte ptr [r9], 0
0x18000416a  mov     rcx, rdx
0x18000416d  mov     dword ptr [r14], 0
0x180004174  mov     rax, [rdx]
0x180004177  mov     rax, [rax+10h]
0x18000417b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004180  mov     ebx, eax
0x180004182  test    eax, eax
0x180004184  jnz     short loc_1800041F6
0x180004186  mov     rax, [rdi]
0x180004189  lea     r9, [rsp+478h+dwDataLen]
0x18000418e  lea     r8, [rsp+478h+pbData]
0x180004193  mov     edx, 400h
0x180004198  mov     rcx, rdi
0x18000419b  mov     rax, [rax+8]
0x18000419f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041a4  mov     ebx, eax
0x1800041a6  test    eax, eax
0x1800041a8  jnz     short loc_1800041D2
0x1800041aa  mov     r8d, [rsp+478h+dwDataLen]; dwDataLen
0x1800041af  lea     rdx, [rsp+478h+pbData]; pbData
0x1800041b4  mov     rcx, [r15]; hHash
0x1800041b7  xor     r9d, r9d; dwFlags
0x1800041ba  call    cs:__imp_CryptHashData
0x1800041c0  test    eax, eax
0x1800041c2  jnz     short loc_1800041CC
0x1800041c4  call    cs:__imp_GetLastError
0x1800041ca  mov     ebx, eax
0x1800041cc  test    ebx, ebx
0x1800041ce  jz      short loc_180004186
0x1800041d0  jmp     short loc_1800041F6
0x1800041d2  cmp     eax, 103h
0x1800041d7  jnz     short loc_1800041F6
0x1800041d9  mov     r9, r14; unsigned int *
0x1800041dc  mov     r8d, 400h; unsigned int
0x1800041e2  mov     rdx, rsi; unsigned __int8 *
0x1800041e5  mov     rcx, r15; this
0x1800041e8  call    ?GetHash@CryptHash@@QEAAKPEAEKPEAK@Z; CryptHash::GetHash(uchar *,ulong,ulong *)
0x1800041ed  mov     ebx, eax
0x1800041ef  jmp     short loc_1800041F6
0x1800041f1  mov     ebx, 57h ; 'W'
0x1800041f6  mov     eax, ebx
0x1800041f8  mov     rcx, [rsp+478h+var_38]
0x180004200  xor     rcx, rsp; StackCookie
0x180004203  call    __security_check_cookie
0x180004208  add     rsp, 450h
0x18000420f  pop     r15
0x180004211  pop     r14
0x180004213  pop     rdi
0x180004214  pop     rsi
0x180004215  pop     rbx
0x180004216  retn
```
