# EdpRpcGetLockSessionWrappedKey

- ea: `0x180004630`
- end: `0x1800047f0`
- name: `EdpRpcGetLockSessionWrappedKey`
- size: `448`
- prototype: `__int64 __fastcall(void *, UCHAR *, __int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180003854`
- `0x180004630`
- `0x18000c392`
- `0x18000c3c0`

## import_xrefs

- `EFSCORE!EdpDllGetLockSessionWrappedKey` at `0x18000478d`
- `EFSCORE!EdpDllGetLockSessionWrappedKey` at `0x18000478d`

## pseudocode

```c
__int64 __fastcall EdpRpcGetLockSessionWrappedKey(
        void *a1,
        UCHAR *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v11; // eax
  int v12; // ecx
  int v13; // edi
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // ecx
  _OWORD *v17; // r9
  _OWORD *v18; // r8
  int LockSessionWrappedKey; // eax
  int v20; // ecx
  _BYTE v24[112]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v25[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v26[2]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(v24, 0, sizeof(v24));
  memset(v26, 0, sizeof(v26));
  memset(v25, 0, sizeof(v25));
  if ( a2 && a3 && a4 )
  {
    if ( a5 && a6 && a7 && a8 )
    {
      v11 = EdpResolveAppHashForAppKeyCaching(a1, a2, (__int64)v26, (__int64)v25);
      v13 = v11;
      if ( v11 >= 0 )
      {
        v15 = EdpBeginLocalOnlyRpcCall((__int64)v24);
        v14 = v15;
        if ( v15 >= 0 )
        {
          v17 = v25;
          v18 = v26;
          if ( v13 )
          {
            v17 = 0;
            v18 = 0;
          }
          LockSessionWrappedKey = EdpDllGetLockSessionWrappedKey(v24, a2, v18, v17, a3, a4, a5, a6, a7, a8);
          v14 = LockSessionWrappedKey;
          if ( LockSessionWrappedKey < 0 )
            fnEfsLogTrace1(v20, (unsigned int)EFS_API_ERROR, LockSessionWrappedKey, 6, 44);
          EdpCleanupLocalOnlyRpcCall((__int64)v24);
        }
        else
        {
          fnEfsLogTrace1(v16, (unsigned int)EFS_API_ERROR, v15, 6, 27);
        }
      }
      else
      {
        v14 = 0;
        fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v11, 6, 21);
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v14;
}

```

## disassembly

```asm
0x180004630  push    rbp
0x180004632  push    rbx
0x180004633  push    rsi
0x180004634  push    rdi
0x180004635  push    r12
0x180004637  push    r13
0x180004639  push    r14
0x18000463b  push    r15
0x18000463d  lea     rbp, [rsp-38h]
0x180004642  sub     rsp, 138h
0x180004649  mov     rax, cs:__security_cookie
0x180004650  xor     rax, rsp
0x180004653  mov     [rbp+70h+var_50], rax
0x180004657  mov     rbx, [rbp+70h+arg_38]
0x18000465e  mov     rdi, rdx
0x180004661  mov     r15, [rbp+70h+arg_20]
0x180004668  mov     rsi, r8
0x18000466b  mov     r12, [rbp+70h+arg_28]
0x180004672  mov     r14d, r9d
0x180004675  mov     r13, [rbp+70h+arg_30]
0x18000467c  mov     [rsp+170h+var_110], rdx
0x180004681  xor     edx, edx; Val
0x180004683  mov     [rsp+170h+var_120], rcx
0x180004688  lea     rcx, [rsp+170h+var_100]; void *
0x18000468d  mov     [rsp+170h+var_118], rbx
0x180004692  lea     r8d, [rdx+70h]; Size
0x180004696  call    memset_0
0x18000469b  xorps   xmm0, xmm0
0x18000469e  xorps   xmm1, xmm1
0x1800046a1  movups  [rbp+70h+var_70], xmm0
0x1800046a5  movups  [rbp+70h+var_60], xmm0
0x1800046a9  movups  [rbp+70h+var_90], xmm1
0x1800046ad  movups  [rbp+70h+var_80], xmm1
0x1800046b1  test    rdi, rdi
0x1800046b4  jz      loc_1800047C9
0x1800046ba  test    rsi, rsi
0x1800046bd  jz      loc_1800047C9
0x1800046c3  test    r14d, r14d
0x1800046c6  jz      loc_1800047C9
0x1800046cc  test    r15, r15
0x1800046cf  jz      loc_1800047C2
0x1800046d5  test    r12, r12
0x1800046d8  jz      loc_1800047C2
0x1800046de  test    r13, r13
0x1800046e1  jz      loc_1800047C2
0x1800046e7  test    rbx, rbx
0x1800046ea  jz      loc_1800047C2
0x1800046f0  mov     rcx, [rsp+170h+var_120]
0x1800046f5  lea     r9, [rbp+70h+var_90]
0x1800046f9  lea     r8, [rbp+70h+var_70]
0x1800046fd  mov     rdx, rdi
0x180004700  call    EdpResolveAppHashForAppKeyCaching
0x180004705  mov     edi, eax
0x180004707  test    eax, eax
0x180004709  jns     short loc_18000472F
0x18000470b  xor     ebx, ebx
0x18000470d  mov     dword ptr [rsp+170h+var_150], 0C15h
0x180004715  mov     r8d, eax
0x180004718  mov     r9d, 6
0x18000471e  lea     rdx, EFS_API_ERROR
0x180004725  call    fnEfsLogTrace1
0x18000472a  jmp     loc_1800047CE
0x18000472f  lea     rcx, [rsp+170h+var_100]
0x180004734  call    EdpBeginLocalOnlyRpcCall
0x180004739  mov     ebx, eax
0x18000473b  test    eax, eax
0x18000473d  jns     short loc_18000474C
0x18000473f  mov     dword ptr [rsp+170h+var_150], 0C1Bh
0x180004747  mov     r8d, eax
0x18000474a  jmp     short loc_180004718
0x18000474c  mov     rdx, [rsp+170h+var_110]
0x180004751  lea     r9, [rbp+70h+var_90]
0x180004755  xor     eax, eax
0x180004757  lea     r8, [rbp+70h+var_70]
0x18000475b  test    edi, edi
0x18000475d  lea     rcx, [rsp+170h+var_100]
0x180004762  cmovnz  r9, rax
0x180004766  cmovnz  r8, rax
0x18000476a  mov     rax, [rsp+170h+var_118]
0x18000476f  mov     [rsp+170h+var_128], rax
0x180004774  mov     [rsp+170h+var_130], r13
0x180004779  mov     [rsp+170h+var_138], r12
0x18000477e  mov     [rsp+170h+var_140], r15
0x180004783  mov     [rsp+170h+var_148], r14d
0x180004788  mov     [rsp+170h+var_150], rsi
0x18000478d  call    cs:__imp_EdpDllGetLockSessionWrappedKey
0x180004793  mov     ebx, eax
0x180004795  test    eax, eax
0x180004797  jns     short loc_1800047B6
0x180004799  mov     r9d, 6
0x18000479f  mov     dword ptr [rsp+170h+var_150], 0C2Ch
0x1800047a7  mov     r8d, eax
0x1800047aa  lea     rdx, EFS_API_ERROR
0x1800047b1  call    fnEfsLogTrace1
0x1800047b6  lea     rcx, [rsp+170h+var_100]
0x1800047bb  call    EdpCleanupLocalOnlyRpcCall
0x1800047c0  jmp     short loc_1800047CE
0x1800047c2  mov     ebx, 80004003h
0x1800047c7  jmp     short loc_1800047CE
0x1800047c9  mov     ebx, 80070057h
0x1800047ce  mov     eax, ebx
0x1800047d0  mov     rcx, [rbp+70h+var_50]
0x1800047d4  xor     rcx, rsp; StackCookie
0x1800047d7  call    __security_check_cookie
0x1800047dc  add     rsp, 138h
0x1800047e3  pop     r15
0x1800047e5  pop     r14
0x1800047e7  pop     r13
0x1800047e9  pop     r12
0x1800047eb  pop     rdi
0x1800047ec  pop     rsi
0x1800047ed  pop     rbx
0x1800047ee  pop     rbp
0x1800047ef  retn
```
