# LpParseProfileNode

- ea: `0x180033490`
- end: `0x180033623`
- name: `LpParseProfileNode`
- size: `403`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180033764`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180032d04`
- `0x180032d9c`
- `0x180033490`
- `0x180033c08`
- `0x18003bcb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033521`

## pseudocode

```c
__int64 __fastcall LpParseProfileNode(struct IXMLDOMNode *a1, _QWORD *a2, __int64 a3)
{
  char *v6; // rsi
  DWORD v7; // ebx
  char *v8; // rbx
  DWORD LastError; // edi
  __int64 v10; // rcx
  _OWORD *v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 50, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids);
  }
  v6 = (char *)Xc_Process_user_allocate(0x230u);
  if ( v6 || (v7 = GetLastError()) == 0 )
  {
    *((_DWORD *)v6 + 5) = 1;
    *((_DWORD *)v6 + 134) = 5304834;
    v8 = (char *)Xc_Process_user_allocate(0x20u);
    if ( v8 || (LastError = GetLastError()) == 0 )
    {
      *(_QWORD *)v8 = 1;
      LastError = XlpParseDot3MsmSettings(a1, (struct _DOT3_MSM_PROFILE *)(v8 + 8));
      if ( !LastError )
      {
        *((_QWORD *)v6 + 69) = v8;
        v7 = 0;
        if ( a2 )
        {
          *a2 = v6;
          goto LABEL_21;
        }
        goto LABEL_15;
      }
      if ( v8 )
        LpFreeDot3ACProfile(v8);
    }
    v7 = LastError;
LABEL_15:
    if ( v6 )
    {
      if ( LastError && a3 )
      {
        v10 = 4;
        *(_DWORD *)(a3 + 512) = 0;
        v11 = v6 + 24;
        do
        {
          v12 = v11[1];
          *(_OWORD *)a3 = *v11;
          v13 = v11[2];
          *(_OWORD *)(a3 + 16) = v12;
          v14 = v11[3];
          *(_OWORD *)(a3 + 32) = v13;
          v15 = v11[4];
          *(_OWORD *)(a3 + 48) = v14;
          v16 = v11[5];
          *(_OWORD *)(a3 + 64) = v15;
          v17 = v11[6];
          *(_OWORD *)(a3 + 80) = v16;
          v18 = v11[7];
          v11 += 8;
          *(_OWORD *)(a3 + 96) = v17;
          *(_OWORD *)(a3 + 112) = v18;
          a3 += 128;
          --v10;
        }
        while ( v10 );
      }
      LpFreeProfile(v6);
    }
  }
LABEL_21:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 51, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180033490  push    rbx
0x180033492  push    rbp
0x180033493  push    rsi
0x180033494  push    rdi
0x180033495  push    r13
0x180033497  push    r14
0x180033499  push    r15
0x18003349b  sub     rsp, 20h
0x18003349f  mov     rbp, r8
0x1800334a2  mov     r14, rdx
0x1800334a5  mov     r15, rcx
0x1800334a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334af  lea     r13, WPP_GLOBAL_Control
0x1800334b6  cmp     rcx, r13
0x1800334b9  jz      short loc_1800334DC
0x1800334bb  cmp     byte ptr [rcx+19h], 4
0x1800334bf  jb      short loc_1800334DC
0x1800334c1  test    byte ptr [rcx+1Ch], 1
0x1800334c5  jz      short loc_1800334DC
0x1800334c7  mov     rcx, [rcx+10h]
0x1800334cb  lea     r8, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids
0x1800334d2  mov     edx, 32h ; '2'
0x1800334d7  call    WPP_SF_
0x1800334dc  mov     ecx, 230h; dwBytes
0x1800334e1  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x1800334e6  mov     rsi, rax
0x1800334e9  test    rax, rax
0x1800334ec  jnz     short loc_1800334FE
0x1800334ee  call    cs:__imp_GetLastError
0x1800334f4  mov     ebx, eax
0x1800334f6  test    eax, eax
0x1800334f8  jnz     loc_1800335E2
0x1800334fe  mov     ecx, 20h ; ' '; dwBytes
0x180033503  mov     dword ptr [rsi+14h], 1
0x18003350a  mov     dword ptr [rsi+218h], 50F202h
0x180033514  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180033519  mov     rbx, rax
0x18003351c  test    rax, rax
0x18003351f  jnz     short loc_18003352D
0x180033521  call    cs:__imp_GetLastError
0x180033527  mov     edi, eax
0x180033529  test    eax, eax
0x18003352b  jnz     short loc_180033569
0x18003352d  lea     rdx, [rbx+8]; struct _DOT3_MSM_PROFILE *
0x180033531  mov     qword ptr [rbx], 1
0x180033538  mov     rcx, r15; struct IXMLDOMNode *
0x18003353b  call    ?XlpParseDot3MsmSettings@@YAKPEAUIXMLDOMNode@@PEAU_DOT3_MSM_PROFILE@@@Z; XlpParseDot3MsmSettings(IXMLDOMNode *,_DOT3_MSM_PROFILE *)
0x180033540  mov     edi, eax
0x180033542  test    eax, eax
0x180033544  jnz     short loc_18003355C
0x180033546  mov     [rsi+228h], rbx
0x18003354d  mov     ebx, eax
0x18003354f  test    r14, r14
0x180033552  jz      short loc_18003356B
0x180033554  mov     [r14], rsi
0x180033557  jmp     loc_1800335E2
0x18003355c  test    rbx, rbx
0x18003355f  jz      short loc_180033569
0x180033561  mov     rcx, rbx; lpMem
0x180033564  call    LpFreeDot3ACProfile
0x180033569  mov     ebx, edi
0x18003356b  test    rsi, rsi
0x18003356e  jz      short loc_1800335E2
0x180033570  test    edi, edi
0x180033572  jz      short loc_1800335DA
0x180033574  test    rbp, rbp
0x180033577  jz      short loc_1800335DA
0x180033579  mov     ecx, 4
0x18003357e  mov     dword ptr [rbp+200h], 0
0x180033588  lea     rax, [rsi+18h]
0x18003358c  lea     edx, [rcx+7Ch]
0x18003358f  movups  xmm0, xmmword ptr [rax]
0x180033592  movups  xmm1, xmmword ptr [rax+10h]
0x180033596  movups  xmmword ptr [rbp+0], xmm0
0x18003359a  movups  xmm0, xmmword ptr [rax+20h]
0x18003359e  movups  xmmword ptr [rbp+10h], xmm1
0x1800335a2  movups  xmm1, xmmword ptr [rax+30h]
0x1800335a6  movups  xmmword ptr [rbp+20h], xmm0
0x1800335aa  movups  xmm0, xmmword ptr [rax+40h]
0x1800335ae  movups  xmmword ptr [rbp+30h], xmm1
0x1800335b2  movups  xmm1, xmmword ptr [rax+50h]
0x1800335b6  movups  xmmword ptr [rbp+40h], xmm0
0x1800335ba  movups  xmm0, xmmword ptr [rax+60h]
0x1800335be  movups  xmmword ptr [rbp+50h], xmm1
0x1800335c2  movups  xmm1, xmmword ptr [rax+70h]
0x1800335c6  add     rax, rdx
0x1800335c9  movups  xmmword ptr [rbp+60h], xmm0
0x1800335cd  movups  xmmword ptr [rbp+70h], xmm1
0x1800335d1  add     rbp, rdx
0x1800335d4  sub     rcx, 1
0x1800335d8  jnz     short loc_18003358F
0x1800335da  mov     rcx, rsi; lpMem
0x1800335dd  call    LpFreeProfile
0x1800335e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335e9  cmp     rcx, r13
0x1800335ec  jz      short loc_180033612
0x1800335ee  cmp     byte ptr [rcx+19h], 4
0x1800335f2  jb      short loc_180033612
0x1800335f4  test    byte ptr [rcx+1Ch], 1
0x1800335f8  jz      short loc_180033612
0x1800335fa  mov     rcx, [rcx+10h]
0x1800335fe  lea     r8, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids
0x180033605  mov     edx, 33h ; '3'
0x18003360a  mov     r9d, ebx
0x18003360d  call    WPP_SF_d
0x180033612  mov     eax, ebx
0x180033614  add     rsp, 20h
0x180033618  pop     r15
0x18003361a  pop     r14
0x18003361c  pop     r13
0x18003361e  pop     rdi
0x18003361f  pop     rsi
0x180033620  pop     rbp
0x180033621  pop     rbx
0x180033622  retn
```
