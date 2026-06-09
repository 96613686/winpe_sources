# SplitRule(void *,_tag_FW_RULE *,ulong)

- ea: `0x18002c6a8`
- end: `0x18002c975`
- name: `?SplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z`
- size: `717`
- prototype: `__int64 __fastcall(void *, struct _tag_FW_RULE *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002c17c`
- `0x18002c4d8`

## callees

- `0x18000994c`
- `0x180021f6c`
- `0x18002c6a8`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c824`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c824`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002c86c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002c86c`
- `FirewallAPI!FWSetFirewallRule` at `0x18002c7c4`
- `FirewallAPI!FWSetFirewallRule` at `0x18002c7c4`
- `FirewallAPI!FWAddFirewallRule` at `0x18002c8c3`
- `FirewallAPI!FWAddFirewallRule` at `0x18002c8c3`
- `FirewallAPI!FwFree` at `0x18002c906`
- `FirewallAPI!FwFree` at `0x18002c906`
- `fwbase!FwStringCopy` at `0x18002c91b`
- `fwbase!FwStringCopy` at `0x18002c91b`

## pseudocode

```c
__int64 __fastcall SplitRule(void *a1, struct _tag_FW_RULE *a2, int a3)
{
  int v6; // r14d
  unsigned int AllProfiles; // eax
  __int64 v8; // rdx
  _OWORD *v9; // rcx
  unsigned int v10; // r8d
  struct _tag_FW_RULE *v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  int v19; // r14d
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int64 v26; // rax
  int v27; // eax
  int v28; // ebx
  CFwCplLua *v29; // rcx
  __int64 v30; // rdx
  int v31; // edi
  int v32; // eax
  OLECHAR *v33; // rcx
  _BYTE v35[16]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR *v36; // [rsp+30h] [rbp-D0h]
  int v37; // [rsp+48h] [rbp-B8h]
  GUID pguid; // [rsp+220h] [rbp+120h] BYREF
  OLECHAR sz[40]; // [rsp+230h] [rbp+130h] BYREF

  pguid = 0;
  memset_0(v35, 0, 0x1F8u);
  memset_0(sz, 0, sizeof(sz));
  v6 = *((_DWORD *)a2 + 10);
  AllProfiles = GetAllProfiles();
  v8 = 3;
  v9 = v35;
  v10 = AllProfiles;
  v11 = a2;
  do
  {
    v12 = *((_OWORD *)v11 + 1);
    *v9 = *(_OWORD *)v11;
    v13 = *((_OWORD *)v11 + 2);
    v9[1] = v12;
    v14 = *((_OWORD *)v11 + 3);
    v9[2] = v13;
    v15 = *((_OWORD *)v11 + 4);
    v9[3] = v14;
    v16 = *((_OWORD *)v11 + 5);
    v9[4] = v15;
    v17 = *((_OWORD *)v11 + 6);
    v9[5] = v16;
    v18 = *((_OWORD *)v11 + 7);
    v11 = (struct _tag_FW_RULE *)((char *)v11 + 128);
    v9[6] = v17;
    v9[7] = v18;
    v9 += 8;
    --v8;
  }
  while ( v8 );
  v19 = v10 & v6;
  v20 = *((_OWORD *)v11 + 1);
  *v9 = *(_OWORD *)v11;
  v21 = *((_OWORD *)v11 + 2);
  v9[1] = v20;
  v22 = *((_OWORD *)v11 + 3);
  v9[2] = v21;
  v23 = *((_OWORD *)v11 + 4);
  v9[3] = v22;
  v24 = *((_OWORD *)v11 + 5);
  v9[4] = v23;
  v25 = *((_OWORD *)v11 + 6);
  v26 = *((_QWORD *)v11 + 14);
  v9[5] = v24;
  v9[6] = v25;
  *((_QWORD *)v9 + 14) = v26;
  v37 = a3 & v19;
  v27 = FWSetFirewallRule(a1, v35);
  v28 = v27;
  if ( !v27 )
    goto LABEL_11;
  if ( v27 > 0 )
    v28 = (unsigned __int16)v27 | 0x80070000;
  if ( v28 < 0 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v30 = 13;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids, (unsigned int)v28);
    }
  }
  else
  {
LABEL_11:
    v28 = CoCreateGuid(&pguid);
    if ( v28 >= 0 )
    {
      if ( StringFromGUID2(&pguid, sz, 40) )
      {
        v31 = v19 & ~a3;
        v36 = sz;
        v37 = v31;
        v32 = FWAddFirewallRule(a1, v35);
        v28 = v32;
        if ( v32 > 0 )
          v28 = (unsigned __int16)v32 | 0x80070000;
        if ( v28 >= 0 )
        {
          FwFree(*((_QWORD *)a2 + 2));
          v33 = v36;
          *((_QWORD *)a2 + 2) = 0;
          v28 = FwStringCopy(v33, (char *)a2 + 16);
          if ( v28 >= 0 )
          {
            *((_DWORD *)a2 + 10) = v31;
            return (unsigned int)v28;
          }
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v30 = 17;
            goto LABEL_10;
          }
        }
        else
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v30 = 16;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v28 = -2147024774;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v30 = 15;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v30 = 14;
        goto LABEL_10;
      }
    }
  }
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x18002c6a8  mov     [rsp-8+arg_18], rbx
0x18002c6ad  push    rbp
0x18002c6ae  push    rsi
0x18002c6af  push    rdi
0x18002c6b0  push    r14
0x18002c6b2  push    r15
0x18002c6b4  lea     rbp, [rsp-190h]
0x18002c6bc  sub     rsp, 290h
0x18002c6c3  mov     rax, cs:__security_cookie
0x18002c6ca  xor     rax, rsp
0x18002c6cd  mov     [rbp+1B0h+var_30], rax
0x18002c6d4  mov     edi, r8d
0x18002c6d7  mov     rsi, rdx
0x18002c6da  mov     r15, rcx
0x18002c6dd  xorps   xmm0, xmm0
0x18002c6e0  xor     edx, edx; Val
0x18002c6e2  lea     rcx, [rsp+2B0h+var_290]; void *
0x18002c6e7  mov     r8d, 1F8h; Size
0x18002c6ed  movups  xmmword ptr [rbp+1B0h+pguid.Data1], xmm0
0x18002c6f4  call    memset_0
0x18002c6f9  xor     edx, edx; Val
0x18002c6fb  lea     rcx, [rbp+1B0h+sz]; void *
0x18002c702  lea     r8d, [rdx+50h]; Size
0x18002c706  call    memset_0
0x18002c70b  mov     r14d, [rsi+28h]
0x18002c70f  call    ?GetAllProfiles@@YAKXZ; GetAllProfiles(void)
0x18002c714  mov     edx, 3
0x18002c719  lea     rcx, [rsp+2B0h+var_290]
0x18002c71e  mov     r8d, eax
0x18002c721  mov     rax, rsi
0x18002c724  lea     r9d, [rdx+7Dh]
0x18002c728  movups  xmm0, xmmword ptr [rax]
0x18002c72b  movups  xmm1, xmmword ptr [rax+10h]
0x18002c72f  movups  xmmword ptr [rcx], xmm0
0x18002c732  movups  xmm0, xmmword ptr [rax+20h]
0x18002c736  movups  xmmword ptr [rcx+10h], xmm1
0x18002c73a  movups  xmm1, xmmword ptr [rax+30h]
0x18002c73e  movups  xmmword ptr [rcx+20h], xmm0
0x18002c742  movups  xmm0, xmmword ptr [rax+40h]
0x18002c746  movups  xmmword ptr [rcx+30h], xmm1
0x18002c74a  movups  xmm1, xmmword ptr [rax+50h]
0x18002c74e  movups  xmmword ptr [rcx+40h], xmm0
0x18002c752  movups  xmm0, xmmword ptr [rax+60h]
0x18002c756  movups  xmmword ptr [rcx+50h], xmm1
0x18002c75a  movups  xmm1, xmmword ptr [rax+70h]
0x18002c75e  add     rax, r9
0x18002c761  movups  xmmword ptr [rcx+60h], xmm0
0x18002c765  movups  xmmword ptr [rcx+70h], xmm1
0x18002c769  add     rcx, r9
0x18002c76c  sub     rdx, 1
0x18002c770  jnz     short loc_18002C728
0x18002c772  movups  xmm0, xmmword ptr [rax]
0x18002c775  and     r14d, r8d
0x18002c778  lea     rdx, [rsp+2B0h+var_290]
0x18002c77d  movups  xmm1, xmmword ptr [rax+10h]
0x18002c781  movups  xmmword ptr [rcx], xmm0
0x18002c784  movups  xmm0, xmmword ptr [rax+20h]
0x18002c788  movups  xmmword ptr [rcx+10h], xmm1
0x18002c78c  movups  xmm1, xmmword ptr [rax+30h]
0x18002c790  movups  xmmword ptr [rcx+20h], xmm0
0x18002c794  movups  xmm0, xmmword ptr [rax+40h]
0x18002c798  movups  xmmword ptr [rcx+30h], xmm1
0x18002c79c  movups  xmm1, xmmword ptr [rax+50h]
0x18002c7a0  movups  xmmword ptr [rcx+40h], xmm0
0x18002c7a4  movups  xmm0, xmmword ptr [rax+60h]
0x18002c7a8  mov     rax, [rax+70h]
0x18002c7ac  movups  xmmword ptr [rcx+50h], xmm1
0x18002c7b0  movups  xmmword ptr [rcx+60h], xmm0
0x18002c7b4  mov     [rcx+70h], rax
0x18002c7b8  mov     eax, r14d
0x18002c7bb  and     eax, edi
0x18002c7bd  mov     rcx, r15
0x18002c7c0  mov     [rsp+2B0h+var_268], eax
0x18002c7c4  call    cs:__imp_FWSetFirewallRule
0x18002c7ca  mov     ebx, eax
0x18002c7cc  test    eax, eax
0x18002c7ce  jz      short loc_18002C81D
0x18002c7d0  jle     short loc_18002C7DB
0x18002c7d2  movzx   ebx, ax
0x18002c7d5  or      ebx, 80070000h
0x18002c7db  test    ebx, ebx
0x18002c7dd  jns     short loc_18002C81D
0x18002c7df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7e6  lea     rax, WPP_GLOBAL_Control
0x18002c7ed  cmp     rcx, rax
0x18002c7f0  jz      loc_18002C94D
0x18002c7f6  test    byte ptr [rcx+1Ch], 1
0x18002c7fa  jz      loc_18002C94D
0x18002c800  mov     edx, 0Dh
0x18002c805  mov     rcx, [rcx+10h]
0x18002c809  lea     r8, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002c810  mov     r9d, ebx
0x18002c813  call    WPP_SF_d
0x18002c818  jmp     loc_18002C94D
0x18002c81d  lea     rcx, [rbp+1B0h+pguid]; pguid
0x18002c824  call    cs:__imp_CoCreateGuid
0x18002c82a  mov     ebx, eax
0x18002c82c  test    eax, eax
0x18002c82e  jns     short loc_18002C858
0x18002c830  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c837  lea     rax, WPP_GLOBAL_Control
0x18002c83e  cmp     rcx, rax
0x18002c841  jz      loc_18002C94D
0x18002c847  test    byte ptr [rcx+1Ch], 1
0x18002c84b  jz      loc_18002C94D
0x18002c851  mov     edx, 0Eh
0x18002c856  jmp     short loc_18002C805
0x18002c858  mov     r8d, 28h ; '('; cchMax
0x18002c85e  lea     rdx, [rbp+1B0h+sz]; lpsz
0x18002c865  lea     rcx, [rbp+1B0h+pguid]; rguid
0x18002c86c  call    cs:__imp_StringFromGUID2
0x18002c872  test    eax, eax
0x18002c874  jnz     short loc_18002C8A6
0x18002c876  mov     ebx, 8007007Ah
0x18002c87b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c882  lea     rax, WPP_GLOBAL_Control
0x18002c889  cmp     rcx, rax
0x18002c88c  jz      loc_18002C94D
0x18002c892  test    byte ptr [rcx+1Ch], 1
0x18002c896  jz      loc_18002C94D
0x18002c89c  mov     edx, 0Fh
0x18002c8a1  jmp     loc_18002C805
0x18002c8a6  lea     rax, [rbp+1B0h+sz]
0x18002c8ad  not     edi
0x18002c8af  and     edi, r14d
0x18002c8b2  mov     [rsp+2B0h+var_280], rax
0x18002c8b7  lea     rdx, [rsp+2B0h+var_290]
0x18002c8bc  mov     [rsp+2B0h+var_268], edi
0x18002c8c0  mov     rcx, r15
0x18002c8c3  call    cs:__imp_FWAddFirewallRule
0x18002c8c9  mov     ebx, eax
0x18002c8cb  test    eax, eax
0x18002c8cd  jle     short loc_18002C8D8
0x18002c8cf  movzx   ebx, ax
0x18002c8d2  or      ebx, 80070000h
0x18002c8d8  test    ebx, ebx
0x18002c8da  jns     short loc_18002C8FF
0x18002c8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8e3  lea     rax, WPP_GLOBAL_Control
0x18002c8ea  cmp     rcx, rax
0x18002c8ed  jz      short loc_18002C94D
0x18002c8ef  test    byte ptr [rcx+1Ch], 1
0x18002c8f3  jz      short loc_18002C94D
0x18002c8f5  mov     edx, 10h
0x18002c8fa  jmp     loc_18002C805
0x18002c8ff  lea     rbx, [rsi+10h]
0x18002c903  mov     rcx, [rbx]
0x18002c906  call    cs:__imp_FwFree
0x18002c90c  mov     rcx, [rsp+2B0h+var_280]
0x18002c911  mov     rdx, rbx
0x18002c914  mov     qword ptr [rbx], 0
0x18002c91b  call    cs:__imp_FwStringCopy
0x18002c921  mov     ebx, eax
0x18002c923  test    eax, eax
0x18002c925  jns     short loc_18002C94A
0x18002c927  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c92e  lea     rax, WPP_GLOBAL_Control
0x18002c935  cmp     rcx, rax
0x18002c938  jz      short loc_18002C94D
0x18002c93a  test    byte ptr [rcx+1Ch], 1
0x18002c93e  jz      short loc_18002C94D
0x18002c940  mov     edx, 11h
0x18002c945  jmp     loc_18002C805
0x18002c94a  mov     [rsi+28h], edi
0x18002c94d  mov     eax, ebx
0x18002c94f  mov     rcx, [rbp+1B0h+var_30]
0x18002c956  xor     rcx, rsp; StackCookie
0x18002c959  call    __security_check_cookie
0x18002c95e  mov     rbx, [rsp+2B0h+arg_18]
0x18002c966  add     rsp, 290h
0x18002c96d  pop     r15
0x18002c96f  pop     r14
0x18002c971  pop     rdi
0x18002c972  pop     rsi
0x18002c973  pop     rbp
0x18002c974  retn
```
