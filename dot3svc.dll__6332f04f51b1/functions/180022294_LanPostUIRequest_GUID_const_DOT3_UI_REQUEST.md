# LanPostUIRequest(_GUID const &,_DOT3_UI_REQUEST *)

- ea: `0x180022294`
- end: `0x180022449`
- name: `?LanPostUIRequest@@YAJAEBU_GUID@@PEAU_DOT3_UI_REQUEST@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _DOT3_UI_REQUEST *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a9ec`

## callees

- `0x1800025f0`
- `0x1800030fc`
- `0x1800084ec`
- `0x18000a8f4`
- `0x18000c230`
- `0x180022294`
- `0x180022450`
- `0x180039f58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002241f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002241f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022315`

## pseudocode

```c
__int64 __fastcall LanPostUIRequest(const struct _GUID *a1, struct _DOT3_UI_REQUEST *a2)
{
  size_t v4; // rbp
  unsigned __int64 v5; // rdx
  SIZE_T v6; // rsi
  char *v7; // rax
  void *v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+20h] [rbp-58h]
  struct _GUID v16; // [rsp+30h] [rbp-48h] BYREF
  struct _GUID v17; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 92, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids);
  }
  v4 = *((unsigned int *)a2 + 4);
  v5 = (unsigned int)(v4 - 1);
  if ( !(_DWORD)v4 )
    v5 = 0;
  v17 = *a1;
  v6 = SafeVariableListBufferSize(0x2Cu, v5, 1u);
  v7 = (char *)CoTaskMemAlloc(v6);
  v8 = v7;
  if ( v7 )
  {
    *(_DWORD *)v7 = v6;
    *((_DWORD *)v7 + 9) = v4;
    *(struct _GUID *)(v7 + 4) = v17;
    *(_OWORD *)(v7 + 20) = xmmword_180045660;
    memcpy_0(v7 + 40, a2, v4);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF__guid_DD(WPP_GLOBAL_Control[1].Flink, v10, v11, &v17, v6, *((_DWORD *)a2 + 5));
    }
    v16 = v17;
    v12 = PublishInterfaceMediaUiRequest(WNF_MUR_MEDIA_UI_REQUEST_LAN, &v16, v8, v6, (unsigned int *)a2 + 5);
    v9 = v12;
    if ( v12 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 94, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids);
      }
      v9 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x544,
        (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\acmapi.cpp",
        (const char *)(unsigned int)v12,
        v15);
    }
    CoTaskMemFree(v8);
  }
  else
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53A,
      (unsigned int)"onecoreuap\\net\\dot3\\ac\\server\\acmapi.cpp",
      (const char *)0x8007000ELL,
      v14);
  }
  return v9;
}

```

## disassembly

```asm
0x180022294  mov     [rsp+arg_10], rbx
0x180022299  mov     [rsp+arg_18], rbp
0x18002229e  push    rsi
0x18002229f  push    rdi
0x1800222a0  push    r12
0x1800222a2  sub     rsp, 60h
0x1800222a6  mov     rax, cs:__security_cookie
0x1800222ad  xor     rax, rsp
0x1800222b0  mov     [rsp+78h+var_28], rax
0x1800222b5  mov     rbx, rdx
0x1800222b8  mov     rdi, rcx
0x1800222bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222c2  lea     r12, WPP_GLOBAL_Control
0x1800222c9  cmp     rcx, r12
0x1800222cc  jz      short loc_1800222EF
0x1800222ce  cmp     byte ptr [rcx+19h], 4
0x1800222d2  jb      short loc_1800222EF
0x1800222d4  test    byte ptr [rcx+1Ch], 1
0x1800222d8  jz      short loc_1800222EF
0x1800222da  mov     rcx, [rcx+10h]
0x1800222de  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x1800222e5  mov     edx, 5Ch ; '\'
0x1800222ea  call    WPP_SF_
0x1800222ef  mov     ebp, [rbx+10h]
0x1800222f2  xor     eax, eax
0x1800222f4  movups  xmm0, xmmword ptr [rdi]
0x1800222f7  test    ebp, ebp
0x1800222f9  lea     edx, [rbp-1]
0x1800222fc  cmovz   edx, eax; unsigned __int64
0x1800222ff  lea     ecx, [rax+2Ch]; unsigned __int64
0x180022302  lea     r8d, [rax+1]; unsigned __int64
0x180022306  movdqu  [rsp+78h+var_38], xmm0
0x18002230c  call    ?SafeVariableListBufferSize@@YAK_K00@Z; SafeVariableListBufferSize(unsigned __int64,unsigned __int64,unsigned __int64)
0x180022311  mov     ecx, eax; cb
0x180022313  mov     esi, eax
0x180022315  call    cs:__imp_CoTaskMemAlloc
0x18002231b  mov     rdi, rax
0x18002231e  test    rax, rax
0x180022321  jnz     short loc_180022346
0x180022323  mov     rcx, [rsp+78h]; this
0x180022328  lea     r8, aOnecoreuapNetD_2; "onecoreuap\\net\\dot3\\ac\\server\\acma"...
0x18002232f  mov     ebx, 8007000Eh
0x180022334  mov     edx, 53Ah; void *
0x180022339  mov     r9d, ebx; char *
0x18002233c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022341  jmp     loc_180022425
0x180022346  mov     [rax], esi
0x180022348  lea     rcx, [rax+28h]; void *
0x18002234c  mov     [rax+24h], ebp
0x18002234f  mov     r8, rbp; Size
0x180022352  movaps  xmm0, [rsp+78h+var_38]
0x180022357  mov     rdx, rbx; Src
0x18002235a  movdqu  xmmword ptr [rax+4], xmm0
0x18002235f  movups  xmm0, cs:xmmword_180045660
0x180022366  movdqu  xmmword ptr [rax+14h], xmm0
0x18002236b  call    memcpy_0
0x180022370  mov     rcx, cs:WPP_GLOBAL_Control
0x180022377  cmp     rcx, r12
0x18002237a  jz      short loc_1800223A1
0x18002237c  cmp     byte ptr [rcx+19h], 4
0x180022380  jb      short loc_1800223A1
0x180022382  test    byte ptr [rcx+1Ch], 1
0x180022386  jz      short loc_1800223A1
0x180022388  mov     eax, [rbx+14h]
0x18002238b  lea     r9, [rsp+78h+var_38]
0x180022390  mov     rcx, [rcx+10h]
0x180022394  mov     [rsp+78h+var_50], eax
0x180022398  mov     dword ptr [rsp+78h+var_58], esi
0x18002239c  call    WPP_SF__guid_DD
0x1800223a1  movaps  xmm0, [rsp+78h+var_38]
0x1800223a6  lea     rax, [rbx+14h]
0x1800223aa  mov     rcx, qword ptr cs:WNF_MUR_MEDIA_UI_REQUEST_LAN.Data; struct _WNF_STATE_NAME
0x1800223b1  lea     rdx, [rsp+78h+var_48]; struct _GUID
0x1800223b6  mov     r9d, esi; unsigned int
0x1800223b9  movdqa  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x1800223bf  mov     r8, rdi; void *
0x1800223c2  mov     [rsp+78h+var_58], rax; int
0x1800223c7  call    ?PublishInterfaceMediaUiRequest@@YAJU_WNF_STATE_NAME@@U_GUID@@PEBXKPEAK@Z; PublishInterfaceMediaUiRequest(_WNF_STATE_NAME,_GUID,void const *,ulong,ulong *)
0x1800223cc  mov     ebx, eax
0x1800223ce  test    eax, eax
0x1800223d0  jns     short loc_1800223ED
0x1800223d2  mov     rcx, [rsp+78h]; this
0x1800223d7  lea     r8, aOnecoreuapNetD_2; "onecoreuap\\net\\dot3\\ac\\server\\acma"...
0x1800223de  mov     r9d, eax; char *
0x1800223e1  mov     edx, 544h; void *
0x1800223e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800223eb  jmp     short loc_18002241C
0x1800223ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223f4  cmp     rcx, r12
0x1800223f7  jz      short loc_18002241A
0x1800223f9  cmp     byte ptr [rcx+19h], 4
0x1800223fd  jb      short loc_18002241A
0x1800223ff  test    byte ptr [rcx+1Ch], 1
0x180022403  jz      short loc_18002241A
0x180022405  mov     rcx, [rcx+10h]
0x180022409  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180022410  mov     edx, 5Eh ; '^'
0x180022415  call    WPP_SF_
0x18002241a  xor     ebx, ebx
0x18002241c  mov     rcx, rdi; pv
0x18002241f  call    cs:__imp_CoTaskMemFree
0x180022425  mov     eax, ebx
0x180022427  mov     rcx, [rsp+78h+var_28]
0x18002242c  xor     rcx, rsp; StackCookie
0x18002242f  call    __security_check_cookie
0x180022434  lea     r11, [rsp+78h+var_18]
0x180022439  mov     rbx, [r11+30h]
0x18002243d  mov     rbp, [r11+38h]
0x180022441  mov     rsp, r11
0x180022444  pop     r12
0x180022446  pop     rdi
0x180022447  pop     rsi
0x180022448  retn
```
