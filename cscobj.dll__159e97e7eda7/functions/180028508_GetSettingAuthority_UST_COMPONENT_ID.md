# GetSettingAuthority(UST_COMPONENT_ID)

- ea: `0x180028508`
- end: `0x180028672`
- name: `?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z`
- size: `362`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ab6c`
- `0x18001ce64`
- `0x18001ee5c`
- `0x180021b60`
- `0x180022030`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180014068`
- `0x180028508`
- `0x180028678`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180028597`
- `OLEAUT32!__imp_VariantInit` at `0x180028597`
- `OLEAUT32!__imp_VariantClear` at `0x18002865f`
- `OLEAUT32!__imp_VariantClear` at `0x18002865f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall GetSettingAuthority(unsigned int a1)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  int v6; // ebx
  __int64 i; // rdx
  const wchar_t *v8; // r9
  BOOL v9; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_313c576492293c0704086ae70e07ed75_Traceguids, a1);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = a1 - 1;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 != 1 )
      {
        if ( (_UNKNOWN *)v2 != &WPP_GLOBAL_Control && (*(_BYTE *)(v2 + 28) & 2) != 0 )
          WPP_SF_(*(_QWORD *)(v2 + 16), 18, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
        return 0;
      }
      v6 = 2;
    }
    else
    {
      v6 = 1;
    }
  }
  else
  {
    v6 = 0;
  }
  VariantInit(&pvarg);
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    if ( LODWORD(qword_1800460D0[9 * i]) == v6 )
    {
      if ( (int)GetUserStateSetting(0, &qword_1800460D0[9 * i], &pvarg) >= 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v8 = L"SA_WMI";
          if ( pvarg.bVal != 1 )
            v8 = L"SA_GP";
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v8);
        }
        v9 = pvarg.bVal == 1;
        goto LABEL_29;
      }
      break;
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_313c576492293c0704086ae70e07ed75_Traceguids);
  v9 = 0;
LABEL_29:
  VariantClear(&pvarg);
  return v9;
}

```

## disassembly

```asm
0x180028508  mov     [rsp+arg_0], rbx
0x18002850d  push    rsi
0x18002850e  sub     rsp, 50h
0x180028512  mov     ebx, ecx
0x180028514  lea     rsi, WPP_GLOBAL_Control
0x18002851b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028522  cmp     rcx, rsi
0x180028525  jz      short loc_18002854C
0x180028527  test    byte ptr [rcx+1Ch], 2
0x18002852b  jz      short loc_18002854C
0x18002852d  mov     edx, 11h
0x180028532  mov     r9d, ebx
0x180028535  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18002853c  mov     rcx, [rcx+10h]
0x180028540  call    WPP_SF_d
0x180028545  mov     rcx, cs:WPP_GLOBAL_Control
0x18002854c  sub     ebx, 1
0x18002854f  jz      short loc_180028590
0x180028551  sub     ebx, 1
0x180028554  jz      short loc_180028589
0x180028556  cmp     ebx, 1
0x180028559  jz      short loc_180028582
0x18002855b  cmp     rcx, rsi
0x18002855e  jz      short loc_18002857B
0x180028560  test    byte ptr [rcx+1Ch], 2
0x180028564  jz      short loc_18002857B
0x180028566  mov     edx, 12h
0x18002856b  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180028572  mov     rcx, [rcx+10h]
0x180028576  call    WPP_SF_
0x18002857b  xor     eax, eax
0x18002857d  jmp     loc_180028667
0x180028582  mov     ebx, 2
0x180028587  jmp     short loc_180028592
0x180028589  mov     ebx, 1
0x18002858e  jmp     short loc_180028592
0x180028590  xor     ebx, ebx
0x180028592  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180028597  call    cs:__imp_VariantInit
0x18002859d  nop
0x18002859e  xor     edx, edx
0x1800285a0  cmp     edx, 3
0x1800285a3  jnb     loc_180028631
0x1800285a9  lea     rcx, [rdx+rdx*8]
0x1800285ad  lea     rax, qword_1800460D0
0x1800285b4  lea     rax, [rax+rcx*8]
0x1800285b8  cmp     [rax], ebx
0x1800285ba  jz      short loc_1800285C0
0x1800285bc  inc     edx
0x1800285be  jmp     short loc_1800285A0
0x1800285c0  mov     [rsp+58h+var_30], 0
0x1800285c9  mov     [rsp+58h+var_38], 0
0x1800285d1  xor     r9d, r9d
0x1800285d4  lea     r8, [rsp+58h+pvarg]
0x1800285d9  mov     rdx, rax
0x1800285dc  xor     ecx, ecx
0x1800285de  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x1800285e3  test    eax, eax
0x1800285e5  js      short loc_180028631
0x1800285e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285ee  cmp     rcx, rsi
0x1800285f1  jz      short loc_180028625
0x1800285f3  test    byte ptr [rcx+1Ch], 2
0x1800285f7  jz      short loc_180028625
0x1800285f9  lea     r9, aSaWmi; "SA_WMI"
0x180028600  lea     rax, aSaGp; "SA_GP"
0x180028607  cmp     byte ptr [rsp+58h+pvarg+8], 1
0x18002860c  cmovnz  r9, rax
0x180028610  mov     edx, 13h
0x180028615  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18002861c  mov     rcx, [rcx+10h]
0x180028620  call    WPP_SF_S
0x180028625  xor     ebx, ebx
0x180028627  cmp     byte ptr [rsp+58h+pvarg+8], 1
0x18002862c  setz    bl
0x18002862f  jmp     short loc_18002865A
0x180028631  mov     rcx, cs:WPP_GLOBAL_Control
0x180028638  cmp     rcx, rsi
0x18002863b  jz      short loc_180028658
0x18002863d  test    byte ptr [rcx+1Ch], 2
0x180028641  jz      short loc_180028658
0x180028643  mov     edx, 14h
0x180028648  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18002864f  mov     rcx, [rcx+10h]
0x180028653  call    WPP_SF_
0x180028658  xor     ebx, ebx
0x18002865a  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18002865f  call    cs:__imp_VariantClear
0x180028665  mov     eax, ebx
0x180028667  mov     rbx, [rsp+58h+arg_0]
0x18002866c  add     rsp, 50h
0x180028670  pop     rsi
0x180028671  retn
```
