# CFaxAccount::GetRegKeyNameForAccount(ushort * *)

- ea: `0x14000d4d4`
- end: `0x14000d678`
- name: `?GetRegKeyNameForAccount@CFaxAccount@@AEBAKPEAPEAG@Z`
- size: `420`
- prototype: `unsigned int __fastcall(CFaxAccount *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cc38`
- `0x14000e0ec`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x14000d4d4`
- `0x140065d14`
- `0x140065dbc`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x14000d529`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000d529`
- `KERNEL32!GetLastError` at `0x14000d536`
- `KERNEL32!GetLastError` at `0x14000d536`
- `KERNEL32!LocalFree` at `0x14000d657`
- `KERNEL32!LocalFree` at `0x14000d657`

## pseudocode

```c
__int64 __fastcall CFaxAccount::GetRegKeyNameForAccount(PSID *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rsi
  DWORD LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  LPWSTR StringSid; // [rsp+70h] [rbp+8h] BYREF

  StringSid = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
  }
  if ( ConvertSidToStringSidW(this[1], &StringSid) )
  {
    v7 = -1;
    do
      ++v7;
    while ( StringSid[v7] );
    v8 = (unsigned int)(v7 + 34);
    v9 = v8;
    v10 = (unsigned __int16 *)pMemAlloc(2 * v8);
    v4 = v10;
    if ( v10 )
    {
      v6 = 0;
      v11 = StringCchPrintfW(v10, v9, L"%s\\%s", L"Software\\Microsoft\\Fax\\Accounts", StringSid);
      v12 = v11;
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
            (unsigned int)v11);
        }
        v6 = (unsigned __int16)v12;
        if ( (v12 & 0x1FFF0000) != 0x70000 )
          v6 = v12;
      }
      *a2 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
          (unsigned int)v8);
      }
      v6 = 8;
    }
  }
  else
  {
    v4 = 0;
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, LastError);
    }
  }
  if ( StringSid )
    LocalFree(StringSid);
  if ( v6 )
    pMemFree(v4);
  return v6;
}

```

## disassembly

```asm
0x14000d4d4  push    rbx
0x14000d4d6  push    rbp
0x14000d4d7  push    rsi
0x14000d4d8  push    rdi
0x14000d4d9  push    r12
0x14000d4db  push    r14
0x14000d4dd  sub     rsp, 38h
0x14000d4e1  xor     ebp, ebp
0x14000d4e3  mov     r14, rdx
0x14000d4e6  mov     [rsp+68h+StringSid], rbp
0x14000d4eb  mov     rbx, rcx
0x14000d4ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d4f5  lea     r12, WPP_GLOBAL_Control
0x14000d4fc  cmp     rcx, r12
0x14000d4ff  jz      short loc_14000D520
0x14000d501  test    byte ptr [rcx+1Ch], 4
0x14000d505  jz      short loc_14000D520
0x14000d507  cmp     byte ptr [rcx+19h], 5
0x14000d50b  jb      short loc_14000D520
0x14000d50d  mov     rcx, [rcx+10h]
0x14000d511  lea     edx, [rbp+11h]
0x14000d514  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d51b  call    WPP_SF_
0x14000d520  mov     rcx, [rbx+8]; Sid
0x14000d524  lea     rdx, [rsp+68h+StringSid]; StringSid
0x14000d529  call    cs:__imp_ConvertSidToStringSidW
0x14000d52f  test    eax, eax
0x14000d531  jnz     short loc_14000D57F
0x14000d533  mov     rsi, rbp
0x14000d536  call    cs:__imp_GetLastError
0x14000d53c  mov     ebx, eax
0x14000d53e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d545  cmp     rcx, r12
0x14000d548  jz      loc_14000D64D
0x14000d54e  test    byte ptr [rcx+1Ch], 4
0x14000d552  jz      loc_14000D64D
0x14000d558  cmp     byte ptr [rcx+19h], 2
0x14000d55c  jb      loc_14000D64D
0x14000d562  mov     rcx, [rcx+10h]
0x14000d566  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d56d  mov     edx, 12h
0x14000d572  mov     r9d, eax
0x14000d575  call    WPP_SF_d
0x14000d57a  jmp     loc_14000D64D
0x14000d57f  mov     rcx, [rsp+68h+StringSid]
0x14000d584  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d588  inc     rax
0x14000d58b  cmp     [rcx+rax*2], bp
0x14000d58f  jnz     short loc_14000D588
0x14000d591  lea     ebx, [rax+22h]
0x14000d594  lea     rcx, [rbx+rbx]; dwBytes
0x14000d598  mov     edi, ebx
0x14000d59a  call    pMemAlloc
0x14000d59f  mov     rsi, rax
0x14000d5a2  test    rax, rax
0x14000d5a5  jnz     short loc_14000D5DC
0x14000d5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d5ae  cmp     rcx, r12
0x14000d5b1  jz      short loc_14000D5D5
0x14000d5b3  test    byte ptr [rcx+1Ch], 4
0x14000d5b7  jz      short loc_14000D5D5
0x14000d5b9  cmp     byte ptr [rcx+19h], 2
0x14000d5bd  jb      short loc_14000D5D5
0x14000d5bf  mov     rcx, [rcx+10h]
0x14000d5c3  lea     edx, [rax+13h]
0x14000d5c6  mov     r9d, ebx
0x14000d5c9  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d5d0  call    WPP_SF_d
0x14000d5d5  mov     ebx, 8
0x14000d5da  jmp     short loc_14000D64D
0x14000d5dc  mov     rax, [rsp+68h+StringSid]
0x14000d5e1  lea     r9, aSoftwareMicros_10; "Software\\Microsoft\\Fax\\Accounts"
0x14000d5e8  lea     r8, aSS_0; "%s\\%s"
0x14000d5ef  mov     [rsp+68h+var_48], rax
0x14000d5f4  mov     rdx, rdi; unsigned __int64
0x14000d5f7  mov     rcx, rsi; unsigned __int16 *
0x14000d5fa  mov     ebx, ebp
0x14000d5fc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d601  mov     edi, eax
0x14000d603  test    eax, eax
0x14000d605  jns     short loc_14000D64A
0x14000d607  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d60e  cmp     rcx, r12
0x14000d611  jz      short loc_14000D637
0x14000d613  test    byte ptr [rcx+1Ch], 4
0x14000d617  jz      short loc_14000D637
0x14000d619  cmp     byte ptr [rcx+19h], 2
0x14000d61d  jb      short loc_14000D637
0x14000d61f  mov     rcx, [rcx+10h]
0x14000d623  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000d62a  mov     edx, 14h
0x14000d62f  mov     r9d, eax
0x14000d632  call    WPP_SF_d
0x14000d637  mov     eax, edi
0x14000d639  movzx   ebx, di
0x14000d63c  and     eax, 1FFF0000h
0x14000d641  cmp     eax, 70000h
0x14000d646  jz      short loc_14000D64A
0x14000d648  mov     ebx, edi
0x14000d64a  mov     [r14], rsi
0x14000d64d  mov     rcx, [rsp+68h+StringSid]; hMem
0x14000d652  test    rcx, rcx
0x14000d655  jz      short loc_14000D65D
0x14000d657  call    cs:__imp_LocalFree
0x14000d65d  test    ebx, ebx
0x14000d65f  jz      short loc_14000D669
0x14000d661  mov     rcx, rsi; lpMem
0x14000d664  call    pMemFree
0x14000d669  mov     eax, ebx
0x14000d66b  add     rsp, 38h
0x14000d66f  pop     r14
0x14000d671  pop     r12
0x14000d673  pop     rdi
0x14000d674  pop     rsi
0x14000d675  pop     rbp
0x14000d676  pop     rbx
0x14000d677  retn
```
