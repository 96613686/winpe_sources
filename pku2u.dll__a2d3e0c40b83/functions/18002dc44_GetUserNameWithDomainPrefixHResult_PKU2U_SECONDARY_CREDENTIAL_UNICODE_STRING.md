# GetUserNameWithDomainPrefixHResult(_PKU2U_SECONDARY_CREDENTIAL *,_UNICODE_STRING *)

- ea: `0x18002dc44`
- end: `0x18002de25`
- name: `?GetUserNameWithDomainPrefixHResult@@YAJPEAU_PKU2U_SECONDARY_CREDENTIAL@@PEAU_UNICODE_STRING@@@Z`
- size: `481`
- prototype: `int(struct _PKU2U_SECONDARY_CREDENTIAL *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007f40`
- `0x180009070`

## callees

- `0x180018870`
- `0x1800264a4`
- `0x18002dc44`
- `0x18002de2c`
- `0x18002e738`
- `0x18002eaa8`
- `0x180044f8c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002dd27`
- `ntdll!RtlLeaveCriticalSection` at `0x18002dd27`
- `ntdll!RtlEnterCriticalSection` at `0x18002dcba`
- `ntdll!RtlEnterCriticalSection` at `0x18002dcba`

## string_xrefs

- `0x18002dc70`: `onecore\ds\security\protocols\pku2u\credapi.cxx`
- `0x18002dd8c`: `onecore\ds\security\protocols\pku2u\credapi.cxx`
- `0x18002de0c`: `onecore\ds\security\protocols\pku2u\credapi.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUserNameWithDomainPrefixHResult(struct _RTL_CRITICAL_SECTION *a1, struct _UNICODE_STRING *a2)
{
  __int64 v3; // rdx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  char *v6; // rdx
  USHORT v7; // di
  WCHAR *v8; // r14
  __int64 v10; // rcx
  unsigned int v11; // r8d
  WCHAR *v12; // rax
  char *v13; // r8
  struct _UNICODE_STRING *p_LockSemaphore; // rcx
  int v15; // eax
  __int128 v16; // [rsp+20h] [rbp-30h] BYREF
  struct _UNICODE_STRING v17; // [rsp+30h] [rbp-20h] BYREF
  struct _RTL_CRITICAL_SECTION **v18; // [rsp+40h] [rbp-10h]
  char v19; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+70h] [rbp+20h] BYREF

  v21 = a1;
  if ( a1 )
  {
    if ( LODWORD(a1->SpinCount) )
    {
      v3 = 1154;
      goto LABEL_3;
    }
    if ( !a1->LockSemaphore )
    {
      v3 = 1155;
      goto LABEL_3;
    }
    if ( !a2 )
    {
      v3 = 1156;
      goto LABEL_3;
    }
    *a2 = 0;
    RtlEnterCriticalSection(a1 + 1);
    v18 = &v21;
    v19 = 1;
    if ( !HIDWORD(v21[2].DebugInfo) )
    {
      v4 = -2147024809;
      v5 = 1163;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
        (const char *)v4,
        v16);
      goto LABEL_15;
    }
    v6 = (char *)v21->LockSemaphore + *((unsigned int *)v21->LockSemaphore + 19);
    v17 = 0;
    v7 = 2 * *((_WORD *)v6 + 4);
    v17.MaximumLength = v7;
    v17.Length = v7;
    v8 = (WCHAR *)&v6[*((unsigned int *)v6 + 1)];
    v17.Buffer = v8;
    if ( v7 )
    {
      v10 = 0;
      v11 = v7 >> 1;
      if ( v11 )
      {
        do
        {
          if ( v8[v10] == 92 )
            break;
          v10 = (unsigned int)(v10 + 1);
        }
        while ( (unsigned int)v10 < v11 );
      }
      if ( (unsigned int)v10 >= v11 )
      {
        v16 = 0;
        WORD1(v16) = 2 * *((_WORD *)v6 + 8);
        LOWORD(v16) = WORD1(v16);
        v13 = &v6[*((unsigned int *)v6 + 3)];
        *((_QWORD *)&v16 + 1) = v13;
        if ( !WORD1(v16) || (p_LockSemaphore = (struct _UNICODE_STRING *)&v16, !v13) )
          p_LockSemaphore = (struct _UNICODE_STRING *)&v21[2].LockSemaphore;
        v15 = WSTBuildFullServiceName(p_LockSemaphore, &v17, a2);
        if ( v15 < 0 )
        {
          v4 = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x4B7,
                 (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
                 (const char *)(unsigned int)v15,
                 v16);
          goto LABEL_15;
        }
      }
      else
      {
        v12 = (WCHAR *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v7);
        a2->Buffer = v12;
        if ( !v12 )
        {
          v4 = -2147024882;
          v5 = 1191;
          goto LABEL_23;
        }
        a2->Length = v7;
        a2->MaximumLength = v7;
        memcpy_0(v12, v8, v7);
      }
    }
    else
    {
      Pku2uLogProvider::NoUserName();
    }
    v4 = 0;
LABEL_15:
    RtlLeaveCriticalSection(v21 + 1);
    return v4;
  }
  v3 = 1153;
LABEL_3:
  v4 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
    (const char *)0x80070057LL,
    v16);
  return v4;
}

```

## disassembly

```asm
0x18002dc44  mov     [rsp-18h+arg_8], rbx
0x18002dc49  mov     [rsp-18h+arg_10], rsi
0x18002dc4e  mov     [rsp-18h+arg_0], rcx
0x18002dc53  push    rbp
0x18002dc54  push    rdi
0x18002dc55  push    r14
0x18002dc57  mov     rbp, rsp
0x18002dc5a  sub     rsp, 50h
0x18002dc5e  mov     rbx, rdx
0x18002dc61  test    rcx, rcx
0x18002dc64  jnz     short loc_18002DC88
0x18002dc66  mov     edx, 481h; void *
0x18002dc6b  mov     ebx, 80070057h
0x18002dc70  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002dc77  mov     r9d, ebx; char *
0x18002dc7a  mov     rcx, [rbp+18h]; this
0x18002dc7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc83  jmp     loc_18002DD2D
0x18002dc88  cmp     dword ptr [rcx+20h], 0
0x18002dc8c  jz      short loc_18002DC95
0x18002dc8e  mov     edx, 482h
0x18002dc93  jmp     short loc_18002DC6B
0x18002dc95  cmp     qword ptr [rcx+18h], 0
0x18002dc9a  jnz     short loc_18002DCA3
0x18002dc9c  mov     edx, 483h
0x18002dca1  jmp     short loc_18002DC6B
0x18002dca3  test    rbx, rbx
0x18002dca6  jnz     short loc_18002DCAF
0x18002dca8  mov     edx, 484h
0x18002dcad  jmp     short loc_18002DC6B
0x18002dcaf  xorps   xmm0, xmm0
0x18002dcb2  movdqu  xmmword ptr [rdx], xmm0
0x18002dcb6  add     rcx, 28h ; '('; CriticalSection
0x18002dcba  call    cs:__imp_RtlEnterCriticalSection
0x18002dcc0  lea     rax, [rbp+arg_0]
0x18002dcc4  mov     [rbp+var_10], rax
0x18002dcc8  mov     [rbp+var_8], 1
0x18002dccc  mov     r9, [rbp+arg_0]
0x18002dcd0  cmp     dword ptr [r9+54h], 0
0x18002dcd5  jnz     short loc_18002DCE6
0x18002dcd7  mov     ebx, 80070057h
0x18002dcdc  mov     edx, 48Bh
0x18002dce1  jmp     loc_18002DD8C
0x18002dce6  mov     rcx, [r9+18h]
0x18002dcea  mov     edx, [rcx+4Ch]
0x18002dced  add     rdx, rcx
0x18002dcf0  xorps   xmm0, xmm0
0x18002dcf3  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x18002dcf7  movzx   edi, word ptr [rdx+8]
0x18002dcfb  add     di, di
0x18002dcfe  mov     [rbp+var_20.MaximumLength], di
0x18002dd02  mov     [rbp+var_20.Length], di
0x18002dd06  mov     r14d, [rdx+4]
0x18002dd0a  add     r14, rdx
0x18002dd0d  mov     [rbp+var_20.Buffer], r14
0x18002dd11  xor     eax, eax
0x18002dd13  cmp     ax, di
0x18002dd16  jnz     short loc_18002DD44
0x18002dd18  call    ?NoUserName@Pku2uLogProvider@@SAXXZ; Pku2uLogProvider::NoUserName(void)
0x18002dd1d  xor     ebx, ebx
0x18002dd1f  mov     rcx, [rbp+arg_0]
0x18002dd23  add     rcx, 28h ; '('; CriticalSection
0x18002dd27  call    cs:__imp_RtlLeaveCriticalSection
0x18002dd2d  mov     eax, ebx
0x18002dd2f  lea     r11, [rsp+50h+var_s0]
0x18002dd34  mov     rbx, [r11+28h]
0x18002dd38  mov     rsi, [r11+30h]
0x18002dd3c  mov     rsp, r11
0x18002dd3f  pop     r14
0x18002dd41  pop     rdi
0x18002dd42  pop     rbp
0x18002dd43  retn
0x18002dd44  xor     ecx, ecx
0x18002dd46  movzx   r8d, di
0x18002dd4a  shr     r8d, 1
0x18002dd4d  jz      short loc_18002DD63
0x18002dd4f  mov     r11d, 5Ch ; '\'
0x18002dd55  cmp     r11w, [r14+rcx*2]
0x18002dd5a  jz      short loc_18002DD63
0x18002dd5c  inc     ecx
0x18002dd5e  cmp     ecx, r8d
0x18002dd61  jb      short loc_18002DD4F
0x18002dd63  cmp     ecx, r8d
0x18002dd66  jnb     short loc_18002DDBE
0x18002dd68  movzx   esi, di
0x18002dd6b  mov     edx, esi; unsigned __int64
0x18002dd6d  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18002dd74  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18002dd79  mov     [rbx+8], rax
0x18002dd7d  test    rax, rax
0x18002dd80  jnz     short loc_18002DDA4
0x18002dd82  mov     ebx, 8007000Eh
0x18002dd87  mov     edx, 4A7h; void *
0x18002dd8c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002dd93  mov     r9d, ebx; char *
0x18002dd96  mov     rcx, [rbp+18h]; this
0x18002dd9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dd9f  jmp     loc_18002DD1F
0x18002dda4  mov     [rbx], di
0x18002dda7  mov     [rbx+2], di
0x18002ddab  mov     r8, rsi; Size
0x18002ddae  mov     rdx, r14; Src
0x18002ddb1  mov     rcx, rax; void *
0x18002ddb4  call    memcpy_0
0x18002ddb9  jmp     loc_18002DD1D
0x18002ddbe  xorps   xmm0, xmm0
0x18002ddc1  movups  [rbp+var_30], xmm0
0x18002ddc5  movzx   ecx, word ptr [rdx+10h]
0x18002ddc9  add     cx, cx
0x18002ddcc  mov     word ptr [rbp+var_30+2], cx
0x18002ddd0  mov     word ptr [rbp+var_30], cx
0x18002ddd4  mov     r8d, [rdx+0Ch]
0x18002ddd8  add     r8, rdx
0x18002dddb  mov     qword ptr [rbp+var_30+8], r8
0x18002dddf  cmp     ax, cx
0x18002dde2  jz      short loc_18002DDED
0x18002dde4  test    r8, r8
0x18002dde7  lea     rcx, [rbp+var_30]
0x18002ddeb  jnz     short loc_18002DDF1
0x18002dded  lea     rcx, [r9+68h]; struct _UNICODE_STRING *
0x18002ddf1  mov     r8, rbx; struct _UNICODE_STRING *
0x18002ddf4  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x18002ddf8  call    ?WSTBuildFullServiceName@@YAJPEAU_UNICODE_STRING@@00@Z; WSTBuildFullServiceName(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x18002ddfd  test    eax, eax
0x18002ddff  jns     loc_18002DD1D
0x18002de05  mov     rcx, [rbp+18h]; this
0x18002de09  mov     r9d, eax; char *
0x18002de0c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002de13  mov     edx, 4B7h; void *
0x18002de18  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002de1d  mov     ebx, eax
0x18002de1f  jmp     loc_18002DD1F
```
