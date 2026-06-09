# SaveRule(_tag_FW_RULE *,void *)

- ea: `0x1800143d8`
- end: `0x18001470c`
- name: `?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z`
- size: `820`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE *, void *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000283c`
- `0x180013e8c`
- `0x180032fe0`
- `0x18003308c`
- `0x18003bd9c`
- `0x180047618`
- `0x1800479f0`

## callees

- `0x180005630`
- `0x180005e0c`
- `0x180009ed0`
- `0x180014110`
- `0x1800143d8`
- `0x180014720`
- `0x1800294b0`
- `0x18002a1f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800145d7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800145d7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001458d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001458d`
- `fwbase!FwBaseFree` at `0x180014499`
- `fwbase!FwBaseFree` at `0x180014499`
- `fwbase!FwStringCopy` at `0x18001463b`
- `fwbase!FwStringCopy` at `0x18001463b`

## pseudocode

```c
__int64 __fastcall SaveRule(struct _tag_FW_RULE *a1, void *a2)
{
  __int64 v2; // r15
  __int16 v4; // r13
  int v6; // r14d
  __int64 v7; // r12
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  int v12; // eax
  FwPolicy2 *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  FwPolicy2 *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // [rsp+20h] [rbp-A8h] BYREF
  GUID pguid; // [rsp+28h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-88h] BYREF

  v2 = *((_QWORD *)a1 + 2);
  v4 = *((_WORD *)a1 + 4);
  v6 = 0;
  pguid = 0;
  memset_0(sz, 0, 0x4Eu);
  v18 = 0;
  if ( v4 == 256 )
  {
    *((_WORD *)a1 + 4) = 512;
    v8 = CoCreateGuid(&pguid);
    if ( v8 >= 0 )
    {
      if ( StringFromGUID2(&pguid, sz, 39) )
      {
        v8 = FwStringCopy(sz, &v18);
        if ( v8 >= 0 )
        {
          v6 = 1;
          *((_QWORD *)a1 + 2) = v18;
          goto LABEL_2;
        }
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_8;
        v17 = 68;
      }
      else
      {
        v8 = -2147418113;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_8;
        v17 = 67;
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_8;
      v17 = 66;
    }
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v8);
    goto LABEL_8;
  }
LABEL_2:
  v7 = *(_QWORD *)a1;
  *(_QWORD *)a1 = 0;
  if ( v6 != 1 )
  {
    v8 = FwRuleUnlocalize(a2, a1);
    if ( v8 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_7;
      v14 = 70;
    }
    else
    {
      v9 = FWSetFirewallRule((__int64)a2, a1);
      v8 = v9;
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      if ( v8 >= 0 )
        goto LABEL_7;
      if ( v8 == -2147024894 )
      {
        v12 = FWAddFirewallRule((__int64)a2, a1);
        v8 = v12;
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        if ( v8 >= 0 )
          goto LABEL_7;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_7;
        v14 = 71;
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_7;
        v14 = 72;
      }
    }
LABEL_45:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v8);
    goto LABEL_7;
  }
  v15 = FWAddFirewallRule((__int64)a2, a1);
  v8 = v15;
  if ( v15 > 0 )
    v8 = (unsigned __int16)v15 | 0x80070000;
  if ( v8 >= 0 )
  {
    FWDeleteFirewallRule((__int64)a2, v2);
    goto LABEL_7;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 69;
    goto LABEL_45;
  }
LABEL_7:
  *(_QWORD *)a1 = v7;
  if ( v8 < 0 )
  {
LABEL_8:
    v10 = v18;
    *((_QWORD *)a1 + 2) = v2;
    *((_WORD *)a1 + 4) = v4;
    goto LABEL_9;
  }
  if ( v6 != 1 )
    return (unsigned int)v8;
  v10 = v2;
LABEL_9:
  FwBaseFree(v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800143d8  mov     [rsp+arg_10], rbx
0x1800143dd  mov     [rsp+arg_18], rbp
0x1800143e2  push    rdi
0x1800143e3  push    r12
0x1800143e5  push    r13
0x1800143e7  push    r14
0x1800143e9  push    r15
0x1800143eb  sub     rsp, 0A0h
0x1800143f2  mov     rax, cs:__security_cookie
0x1800143f9  xor     rax, rsp
0x1800143fc  mov     [rsp+0C8h+var_38], rax
0x180014404  mov     r15, [rcx+10h]
0x180014408  mov     rbp, rdx
0x18001440b  movzx   r13d, word ptr [rcx+8]
0x180014410  mov     rdi, rcx
0x180014413  xorps   xmm0, xmm0
0x180014416  lea     rcx, [rsp+0C8h+sz]; void *
0x18001441b  xor     r14d, r14d
0x18001441e  xor     edx, edx; Val
0x180014420  movups  xmmword ptr [rsp+0C8h+pguid.Data1], xmm0
0x180014425  lea     r8d, [r14+4Eh]; Size
0x180014429  call    memset_0
0x18001442e  mov     eax, 100h
0x180014433  mov     [rsp+0C8h+var_A8], r14
0x180014438  cmp     r13w, ax
0x18001443c  jz      loc_180014582
0x180014442  mov     r12, [rdi]
0x180014445  mov     rdx, rdi; Src
0x180014448  mov     qword ptr [rdi], 0
0x18001444f  mov     rcx, rbp; __int64
0x180014452  cmp     r14d, 1
0x180014456  jz      loc_18001453B
0x18001445c  call    ?FwRuleUnlocalize@@YAJPEAXPEAU_tag_FW_RULE@@@Z; FwRuleUnlocalize(void *,_tag_FW_RULE *)
0x180014461  mov     ebx, eax
0x180014463  test    eax, eax
0x180014465  js      loc_180014694
0x18001446b  mov     rdx, rdi; Src
0x18001446e  mov     rcx, rbp; __int64
0x180014471  call    FWSetFirewallRule
0x180014476  mov     ebx, eax
0x180014478  test    eax, eax
0x18001447a  jg      short loc_1800144D5
0x18001447c  test    ebx, ebx
0x18001447e  js      short loc_1800144E0
0x180014480  mov     [rdi], r12
0x180014483  test    ebx, ebx
0x180014485  jns     loc_1800146FA
0x18001448b  mov     rcx, [rsp+0C8h+var_A8]
0x180014490  mov     [rdi+10h], r15
0x180014494  mov     [rdi+8], r13w
0x180014499  call    cs:__imp_FwBaseFree
0x1800144a0  nop     dword ptr [rax+rax+00h]
0x1800144a5  mov     eax, ebx
0x1800144a7  mov     rcx, [rsp+0C8h+var_38]
0x1800144af  xor     rcx, rsp; StackCookie
0x1800144b2  call    __security_check_cookie
0x1800144b7  lea     r11, [rsp+0C8h+var_28]
0x1800144bf  mov     rbx, [r11+40h]
0x1800144c3  mov     rbp, [r11+48h]
0x1800144c7  mov     rsp, r11
0x1800144ca  pop     r15
0x1800144cc  pop     r14
0x1800144ce  pop     r13
0x1800144d0  pop     r12
0x1800144d2  pop     rdi
0x1800144d3  retn
0x1800144d5  movzx   ebx, ax
0x1800144d8  or      ebx, 80070000h
0x1800144de  jmp     short loc_18001447C
0x1800144e0  cmp     ebx, 80070002h
0x1800144e6  jnz     loc_1800146BC
0x1800144ec  mov     rdx, rdi; Src
0x1800144ef  mov     rcx, rbp; __int64
0x1800144f2  call    FWAddFirewallRule
0x1800144f7  mov     ebx, eax
0x1800144f9  test    eax, eax
0x1800144fb  jg      short loc_180014530
0x1800144fd  test    ebx, ebx
0x1800144ff  jns     loc_180014480
0x180014505  mov     rcx, cs:WPP_GLOBAL_Control
0x18001450c  lea     rax, WPP_GLOBAL_Control
0x180014513  cmp     rcx, rax
0x180014516  jz      loc_180014480
0x18001451c  test    byte ptr [rcx+1Ch], 1
0x180014520  jz      loc_180014480
0x180014526  mov     edx, 47h ; 'G'
0x18001452b  jmp     loc_1800146E2
0x180014530  movzx   ebx, ax
0x180014533  or      ebx, 80070000h
0x180014539  jmp     short loc_1800144FD
0x18001453b  call    FWAddFirewallRule
0x180014540  mov     ebx, eax
0x180014542  test    eax, eax
0x180014544  jle     short loc_18001454F
0x180014546  movzx   ebx, ax
0x180014549  or      ebx, 80070000h
0x18001454f  test    ebx, ebx
0x180014551  jns     loc_180014684
0x180014557  mov     rcx, cs:WPP_GLOBAL_Control
0x18001455e  lea     rax, WPP_GLOBAL_Control
0x180014565  cmp     rcx, rax
0x180014568  jz      loc_180014480
0x18001456e  test    byte ptr [rcx+1Ch], 1
0x180014572  jz      loc_180014480
0x180014578  mov     edx, 45h ; 'E'
0x18001457d  jmp     loc_1800146E2
0x180014582  lea     rcx, [rsp+0C8h+pguid]; pguid
0x180014587  mov     word ptr [rdi+8], 200h
0x18001458d  call    cs:__imp_CoCreateGuid
0x180014594  nop     dword ptr [rax+rax+00h]
0x180014599  mov     ebx, eax
0x18001459b  test    eax, eax
0x18001459d  jns     short loc_1800145C7
0x18001459f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145a6  lea     rax, WPP_GLOBAL_Control
0x1800145ad  cmp     rcx, rax
0x1800145b0  jz      loc_18001448B
0x1800145b6  test    byte ptr [rcx+1Ch], 1
0x1800145ba  jz      loc_18001448B
0x1800145c0  mov     edx, 42h ; 'B'
0x1800145c5  jmp     short loc_180014619
0x1800145c7  mov     r8d, 27h ; '''; cchMax
0x1800145cd  lea     rdx, [rsp+0C8h+sz]; lpsz
0x1800145d2  lea     rcx, [rsp+0C8h+pguid]; rguid
0x1800145d7  call    cs:__imp_StringFromGUID2
0x1800145de  nop     dword ptr [rax+rax+00h]
0x1800145e3  test    eax, eax
0x1800145e5  jnz     short loc_180014631
0x1800145e7  mov     ebx, 8000FFFFh
0x1800145ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145f3  lea     rax, WPP_GLOBAL_Control
0x1800145fa  cmp     rcx, rax
0x1800145fd  jz      loc_18001448B
0x180014603  test    byte ptr [rcx+1Ch], 1
0x180014607  jz      loc_18001448B
0x18001460d  mov     edx, 43h ; 'C'
0x180014612  jmp     short loc_180014619
0x180014614  mov     edx, 44h ; 'D'
0x180014619  mov     rcx, [rcx+10h]
0x18001461d  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180014624  mov     r9d, ebx
0x180014627  call    WPP_SF_d
0x18001462c  jmp     loc_18001448B
0x180014631  lea     rdx, [rsp+0C8h+var_A8]
0x180014636  lea     rcx, [rsp+0C8h+sz]
0x18001463b  call    cs:__imp_FwStringCopy
0x180014642  nop     dword ptr [rax+rax+00h]
0x180014647  mov     ebx, eax
0x180014649  test    eax, eax
0x18001464b  jns     short loc_180014670
0x18001464d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014654  lea     rax, WPP_GLOBAL_Control
0x18001465b  cmp     rcx, rax
0x18001465e  jz      loc_18001448B
0x180014664  test    byte ptr [rcx+1Ch], 1
0x180014668  jz      loc_18001448B
0x18001466e  jmp     short loc_180014614
0x180014670  mov     rax, [rsp+0C8h+var_A8]
0x180014675  mov     r14d, 1
0x18001467b  mov     [rdi+10h], rax
0x18001467f  jmp     loc_180014442
0x180014684  mov     rdx, r15
0x180014687  mov     rcx, rbp
0x18001468a  call    FWDeleteFirewallRule
0x18001468f  jmp     loc_180014480
0x180014694  mov     rcx, cs:WPP_GLOBAL_Control
0x18001469b  lea     rax, WPP_GLOBAL_Control
0x1800146a2  cmp     rcx, rax
0x1800146a5  jz      loc_180014480
0x1800146ab  test    byte ptr [rcx+1Ch], 1
0x1800146af  jz      loc_180014480
0x1800146b5  mov     edx, 46h ; 'F'
0x1800146ba  jmp     short loc_1800146E2
0x1800146bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146c3  lea     rax, WPP_GLOBAL_Control
0x1800146ca  cmp     rcx, rax
0x1800146cd  jz      loc_180014480
0x1800146d3  test    byte ptr [rcx+1Ch], 1
0x1800146d7  jz      loc_180014480
0x1800146dd  mov     edx, 48h ; 'H'
0x1800146e2  mov     rcx, [rcx+10h]
0x1800146e6  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x1800146ed  mov     r9d, ebx
0x1800146f0  call    WPP_SF_d
0x1800146f5  jmp     loc_180014480
0x1800146fa  cmp     r14d, 1
0x1800146fe  jnz     loc_1800144A5
0x180014704  mov     rcx, r15
0x180014707  jmp     loc_180014499
```
