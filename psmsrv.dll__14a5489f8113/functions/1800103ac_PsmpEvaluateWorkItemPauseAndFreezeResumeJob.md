# PsmpEvaluateWorkItemPauseAndFreezeResumeJob

- ea: `0x1800103ac`
- end: `0x1800105f7`
- name: `PsmpEvaluateWorkItemPauseAndFreezeResumeJob`
- size: `587`
- prototype: `void __fastcall(__int64, int, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e0f4`
- `0x180010228`
- `0x180017260`
- `0x180017da0`

## callees

- `0x180009b40`
- `0x18000a750`
- `0x18000defc`
- `0x18000e2cc`
- `0x1800103ac`
- `0x180014a30`
- `0x180014f7c`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010484`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010484`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800104a9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800105ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800104a9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800105ae`

## pseudocode

```c
void __fastcall PsmpEvaluateWorkItemPauseAndFreezeResumeJob(__int64 a1, int a2, __int64 a3)
{
  int v5; // edx
  int v6; // edx
  __int64 v7; // r12
  unsigned int v8; // r13d
  int v9; // eax
  int v10; // esi
  volatile signed __int32 *v11; // r14
  _BYTE *v12; // rbp
  bool v13; // zf
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  int v17; // r9d
  __int128 v18; // [rsp+20h] [rbp-58h] BYREF

  v18 = 0;
  v5 = a2 - 1;
  if ( !v5 )
  {
    v7 = *(_QWORD *)(a1 + 192);
    v8 = 4;
    v9 = 1024;
    v10 = 2;
LABEL_10:
    v11 = (volatile signed __int32 *)(a1 + 132);
    v12 = (_BYTE *)(a1 + 132);
    goto LABEL_6;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
      return;
    v7 = *(_QWORD *)(a1 + 200);
    v8 = 2;
    v9 = 2048;
    v10 = 8;
    goto LABEL_10;
  }
  v7 = 0;
  v8 = 1;
  v9 = 8;
  v10 = 4;
  if ( a3 )
    v7 = *(_QWORD *)(a3 + 48);
  v11 = (volatile signed __int32 *)(a3 + 84);
  v12 = (_BYTE *)(a1 + 132);
LABEL_6:
  if ( !v7 || (v9 & *v11) != 0 )
    return;
  RtlAcquireSRWLockExclusive(a1 + 328);
  if ( v10 != 4 )
  {
    if ( v10 == 2 )
    {
      if ( (*v12 & 4) == 0 )
      {
        v15 = *(_DWORD *)(a1 + 136);
        if ( *(_DWORD *)(a1 + 6784) == v15 )
        {
          if ( v15 )
          {
            v16 = *(_DWORD *)(a1 + 344);
            if ( ((v16 - 1) & 0xFFFFFFFC) == 0 && v16 != 3 )
              goto LABEL_34;
          }
        }
        if ( (*v12 & 4) == 0 )
          goto LABEL_18;
      }
      v13 = *(_DWORD *)(a1 + 6784) == *(_DWORD *)(a1 + 136);
      goto LABEL_17;
    }
    if ( (*(_BYTE *)(a1 + 132) & 2) != 0
      || !*(_DWORD *)(a1 + 144)
      || !(unsigned __int8)PsmpIsApplicationOverQuota(a1, 1) && *(_DWORD *)(a1 + 6788) != v17 )
    {
      if ( (*v12 & 2) == 0 || (unsigned __int8)PsmpIsApplicationOverQuota(a1, 1) )
        goto LABEL_18;
      v13 = *(_DWORD *)(a1 + 6788) == *(_DWORD *)(a1 + 144);
      goto LABEL_17;
    }
LABEL_34:
    BYTE4(v18) = 1;
    goto LABEL_43;
  }
  if ( !a3 )
  {
LABEL_18:
    RtlReleaseSRWLockExclusive(a1 + 328);
    return;
  }
  if ( (*(_BYTE *)(a3 + 84) & 1) != 0 )
    goto LABEL_16;
  v14 = *(_DWORD *)(a3 + 76);
  if ( *(_DWORD *)(a3 + 80) == v14 && v14 )
    goto LABEL_34;
  if ( (*(_BYTE *)(a3 + 84) & 1) == 0 )
    goto LABEL_18;
LABEL_16:
  v13 = *(_DWORD *)(a3 + 80) == *(_DWORD *)(a3 + 76);
LABEL_17:
  if ( v13 )
    goto LABEL_18;
  BYTE4(v18) = 0;
LABEL_43:
  LODWORD(v18) = 1;
  if ( (int)PsmpAdjustJobState(v7, &v18) < 0 )
    goto LABEL_18;
  _InterlockedXor(v11, v8);
  RtlReleaseSRWLockExclusive(a1 + 328);
  if ( BYTE4(v18) )
  {
    PsmpReferenceApplication(a1);
    if ( a3 )
      PsmpReferenceHostContext(a3);
  }
  else
  {
    if ( a3 )
      PsmpDereferenceHostContext((__int64 *)a3, 0);
    PsmpDereferenceApplicationEx(a1, 0);
  }
}

```

## disassembly

```asm
0x1800103ac  mov     [rsp+arg_8], rbx
0x1800103b1  push    rbp
0x1800103b2  push    rsi
0x1800103b3  push    rdi
0x1800103b4  push    r12
0x1800103b6  push    r13
0x1800103b8  push    r14
0x1800103ba  push    r15
0x1800103bc  sub     rsp, 40h
0x1800103c0  mov     rax, cs:__security_cookie
0x1800103c7  xor     rax, rsp
0x1800103ca  mov     [rsp+78h+var_48], rax
0x1800103cf  mov     rbx, rcx
0x1800103d2  mov     ecx, 4
0x1800103d7  xorps   xmm0, xmm0
0x1800103da  mov     rdi, r8
0x1800103dd  movups  [rsp+78h+var_58], xmm0
0x1800103e2  lea     r8d, [rcx-2]
0x1800103e6  lea     r9d, [rcx+4]
0x1800103ea  sub     edx, 1
0x1800103ed  jz      short loc_180010443
0x1800103ef  sub     edx, 1
0x1800103f2  jnz     short loc_180010461
0x1800103f4  xor     r12d, r12d
0x1800103f7  lea     r13d, [rcx-3]
0x1800103fb  mov     eax, r9d
0x1800103fe  mov     esi, ecx
0x180010400  test    rdi, rdi
0x180010403  jz      short loc_180010409
0x180010405  mov     r12, [rdi+30h]
0x180010409  lea     r14, [rdi+54h]
0x18001040d  lea     rbp, [rbx+84h]
0x180010414  test    r12, r12
0x180010417  jz      short loc_18001041E
0x180010419  test    [r14], eax
0x18001041c  jz      short loc_18001047A
0x18001041e  mov     rcx, [rsp+78h+var_48]
0x180010423  xor     rcx, rsp; StackCookie
0x180010426  call    __security_check_cookie
0x18001042b  mov     rbx, [rsp+78h+arg_8]
0x180010433  add     rsp, 40h
0x180010437  pop     r15
0x180010439  pop     r14
0x18001043b  pop     r13
0x18001043d  pop     r12
0x18001043f  pop     rdi
0x180010440  pop     rsi
0x180010441  pop     rbp
0x180010442  retn
0x180010443  mov     r12, [rbx+0C0h]
0x18001044a  mov     r13d, ecx
0x18001044d  mov     eax, 400h
0x180010452  mov     esi, r8d
0x180010455  lea     r14, [rbx+84h]
0x18001045c  mov     rbp, r14
0x18001045f  jmp     short loc_180010414
0x180010461  cmp     edx, 1
0x180010464  jnz     short loc_18001041E
0x180010466  mov     r12, [rbx+0C8h]
0x18001046d  mov     r13d, r8d
0x180010470  mov     eax, 800h
0x180010475  mov     esi, r9d
0x180010478  jmp     short loc_180010455
0x18001047a  lea     r15, [rbx+148h]
0x180010481  mov     rcx, r15
0x180010484  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001048a  cmp     esi, 4
0x18001048d  jnz     short loc_1800104B4
0x18001048f  test    rdi, rdi
0x180010492  jz      short loc_1800104A6
0x180010494  test    byte ptr [rdi+54h], 1
0x180010498  jz      short loc_1800104D1
0x18001049a  mov     eax, [rdi+4Ch]
0x18001049d  cmp     [rdi+50h], eax
0x1800104a0  jnz     loc_180010585
0x1800104a6  mov     rcx, r15
0x1800104a9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800104af  jmp     loc_18001041E
0x1800104b4  cmp     esi, 2
0x1800104b7  jnz     loc_180010543
0x1800104bd  test    byte ptr [rbp+0], 4
0x1800104c1  jz      short loc_1800104E5
0x1800104c3  mov     eax, [rbx+88h]
0x1800104c9  cmp     [rbx+1A80h], eax
0x1800104cf  jmp     short loc_1800104A0
0x1800104d1  mov     eax, [rdi+4Ch]
0x1800104d4  cmp     [rdi+50h], eax
0x1800104d7  jnz     short loc_1800104DD
0x1800104d9  test    eax, eax
0x1800104db  jnz     short loc_18001053C
0x1800104dd  test    byte ptr [rdi+54h], 1
0x1800104e1  jz      short loc_1800104A6
0x1800104e3  jmp     short loc_18001049A
0x1800104e5  mov     eax, [rbx+88h]
0x1800104eb  cmp     [rbx+1A80h], eax
0x1800104f1  jz      loc_18001057B
0x1800104f7  test    byte ptr [rbp+0], 4
0x1800104fb  jz      short loc_1800104A6
0x1800104fd  jmp     short loc_1800104C3
0x1800104ff  test    byte ptr [rbp+0], 2
0x180010503  jz      short loc_1800104A6
0x180010505  mov     edx, 1
0x18001050a  mov     rcx, rbx
0x18001050d  call    PsmpIsApplicationOverQuota
0x180010512  test    al, al
0x180010514  jnz     short loc_1800104A6
0x180010516  mov     eax, [rbx+90h]
0x18001051c  cmp     [rbx+1A84h], eax
0x180010522  jmp     loc_1800104A0
0x180010527  mov     ecx, [rbx+158h]
0x18001052d  lea     eax, [rcx-1]
0x180010530  test    eax, 0FFFFFFFCh
0x180010535  jnz     short loc_1800104F7
0x180010537  cmp     ecx, 3
0x18001053a  jz      short loc_1800104F7
0x18001053c  mov     byte ptr [rsp+78h+var_58+4], 1
0x180010541  jmp     short loc_18001058A
0x180010543  cmp     esi, 8
0x180010546  jnz     loc_1800104A6
0x18001054c  test    byte ptr [rbx+84h], 2
0x180010553  jnz     short loc_1800104FF
0x180010555  mov     r9d, [rbx+90h]
0x18001055c  test    r9d, r9d
0x18001055f  jz      short loc_1800104FF
0x180010561  lea     edx, [rsi-7]
0x180010564  mov     rcx, rbx
0x180010567  call    PsmpIsApplicationOverQuota
0x18001056c  test    al, al
0x18001056e  jnz     short loc_18001053C
0x180010570  cmp     [rbx+1A84h], r9d
0x180010577  jz      short loc_18001053C
0x180010579  jmp     short loc_1800104FF
0x18001057b  test    eax, eax
0x18001057d  jz      loc_1800104F7
0x180010583  jmp     short loc_180010527
0x180010585  mov     byte ptr [rsp+78h+var_58+4], 0
0x18001058a  lea     rdx, [rsp+78h+var_58]
0x18001058f  mov     dword ptr [rsp+78h+var_58], 1
0x180010597  mov     rcx, r12
0x18001059a  call    PsmpAdjustJobState
0x18001059f  test    eax, eax
0x1800105a1  js      loc_1800104A6
0x1800105a7  lock xor [r14], r13d
0x1800105ab  mov     rcx, r15
0x1800105ae  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800105b4  cmp     byte ptr [rsp+78h+var_58+4], 0
0x1800105b9  jz      short loc_1800105D9
0x1800105bb  mov     rcx, rbx
0x1800105be  call    PsmpReferenceApplication
0x1800105c3  test    rdi, rdi
0x1800105c6  jz      loc_18001041E
0x1800105cc  mov     rcx, rdi
0x1800105cf  call    PsmpReferenceHostContext
0x1800105d4  jmp     loc_18001041E
0x1800105d9  test    rdi, rdi
0x1800105dc  jz      short loc_1800105E8
0x1800105de  xor     edx, edx
0x1800105e0  mov     rcx, rdi
0x1800105e3  call    PsmpDereferenceHostContext
0x1800105e8  xor     edx, edx
0x1800105ea  mov     rcx, rbx
0x1800105ed  call    PsmpDereferenceApplicationEx
0x1800105f2  jmp     loc_18001041E
```
