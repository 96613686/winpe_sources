# KampUpdateTimeEventHelper

- ea: `0x180005120`
- end: `0x180005484`
- name: `KampUpdateTimeEventHelper`
- size: `868`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800015e0`
- `0x1800033c4`
- `0x180006540`
- `0x18001f618`
- `0x18001fbe8`

## callees

- `0x180005120`
- `0x18000a0a0`
- `0x18001c500`
- `0x18001d09c`
- `0x18001e368`
- `0x180020444`
- `0x180020494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800051ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800051ca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800051d9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800052bf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800051d9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800052bf`
- `TimeBrokerClient!TbUpdateEvent` at `0x1800052ab`
- `TimeBrokerClient!TbUpdateEvent` at `0x1800052ab`

## string_xrefs

- `0x180005349`: `Kam:KampUpdateTimeEventHelper finished`
- `0x180005410`: `Kam:KampUpdateTimeEventHelper failed to revert`

## pseudocode

```c
__int64 __fastcall KampUpdateTimeEventHelper(__int64 a1)
{
  PVOID *v2; // rbx
  unsigned int v3; // esi
  int v4; // r14d
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 v6; // rcx
  __int128 v7; // xmm0
  DWORD updated; // eax
  DWORD v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  bool v16; // [rsp+20h] [rbp-E0h]
  __int128 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  __int128 v22; // [rsp+80h] [rbp-80h]
  __int128 v23; // [rsp+90h] [rbp-70h]
  __int128 v24; // [rsp+A0h] [rbp-60h]
  __int128 v25; // [rsp+B0h] [rbp-50h]
  __int128 v26; // [rsp+C0h] [rbp-40h]
  __int128 v27; // [rsp+D0h] [rbp-30h]
  __int128 v28; // [rsp+E0h] [rbp-20h]
  __int128 v29; // [rsp+F0h] [rbp-10h]
  __int128 v30; // [rsp+100h] [rbp+0h]
  __int128 v31; // [rsp+110h] [rbp+10h]
  __int128 v32; // [rsp+120h] [rbp+20h]
  __int64 v33; // [rsp+130h] [rbp+30h]
  _OWORD v34[15]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v35; // [rsp+230h] [rbp+130h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  memset_0(&v18, 0, 0xF8u);
  v3 = 60 * *(_DWORD *)(a1 + 372);
  v4 = *(_DWORD *)(a1 + 364);
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    v16 = v4 != 0;
    WPP_SF_dc(v2[2], 40, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v3, v16);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  LODWORD(v18) = 3;
  DWORD2(v18) = v3;
  LODWORD(v19) = 60;
  DWORD1(v19) = v4;
  HIDWORD(v18) = 4 * v3 / 0x64;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_dd(v2[2], 41, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, 4 * v3 / 0x64, 60);
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( SetThreadToken(0, *(HANDLE *)(a1 + 224)) )
  {
    v6 = *(_QWORD *)(a1 + 240);
    v34[0] = v18;
    v35 = v33;
    v34[2] = v20;
    v34[4] = v22;
    v34[1] = v19;
    v34[6] = v24;
    v34[3] = v21;
    v34[8] = v26;
    v34[5] = v23;
    v34[10] = v28;
    v34[7] = v25;
    v34[12] = v30;
    v34[9] = v27;
    v34[14] = v32;
    v7 = *(_OWORD *)(a1 + 308);
    v34[11] = v29;
    v17 = v7;
    v34[13] = v31;
    updated = TbUpdateEvent(v6, &v17, v34);
    v9 = updated;
    if ( updated
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, updated);
    }
    if ( !SetThreadToken(0, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v15, v14, L"Kam:KampUpdateTimeEventHelper failed to revert", LastError);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v9);
      }
    }
  }
  else
  {
    v9 = GetLastError();
  }
  EnterCriticalSection(v5);
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v11, v10, L"Kam:KampUpdateTimeEventHelper finished", v9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180005120  push    rbp
0x180005122  push    rbx
0x180005123  push    rsi
0x180005124  push    rdi
0x180005125  push    r14
0x180005127  push    r15
0x180005129  lea     rbp, [rsp-148h]
0x180005131  sub     rsp, 248h
0x180005138  mov     rdi, rcx
0x18000513b  mov     rbx, cs:WPP_GLOBAL_Control
0x180005142  lea     r15, WPP_GLOBAL_Control
0x180005149  cmp     rbx, r15
0x18000514c  jnz     loc_180005311
0x180005152  xor     edx, edx; Val
0x180005154  lea     rcx, [rsp+270h+var_230]; void *
0x180005159  mov     r8d, 0F8h; Size
0x18000515f  call    memset_0
0x180005164  imul    esi, [rdi+174h], 3Ch ; '<'
0x18000516b  mov     r14d, [rdi+16Ch]
0x180005172  cmp     rbx, r15
0x180005175  jz      short loc_180005181
0x180005177  test    byte ptr [rbx+1Ch], 1
0x18000517b  jnz     loc_180005357
0x180005181  lea     ecx, ds:0[rsi*4]
0x180005188  mov     dword ptr [rsp+270h+var_230], 3
0x180005190  mov     eax, 51EB851Fh
0x180005195  mov     dword ptr [rsp+270h+var_230+8], esi
0x180005199  mul     ecx
0x18000519b  mov     dword ptr [rsp+270h+var_220], 3Ch ; '<'
0x1800051a3  mov     r9d, edx
0x1800051a6  mov     dword ptr [rsp+270h+var_220+4], r14d
0x1800051ab  shr     r9d, 5
0x1800051af  mov     dword ptr [rsp+270h+var_230+0Ch], r9d
0x1800051b4  cmp     rbx, r15
0x1800051b7  jz      short loc_1800051C3
0x1800051b9  test    byte ptr [rbx+1Ch], 1
0x1800051bd  jnz     loc_18000538F
0x1800051c3  lea     rbx, [rdi+18h]
0x1800051c7  mov     rcx, rbx; lpCriticalSection
0x1800051ca  call    cs:__imp_LeaveCriticalSection
0x1800051d0  mov     rdx, [rdi+0E0h]; Token
0x1800051d7  xor     ecx, ecx; Thread
0x1800051d9  call    cs:__imp_SetThreadToken
0x1800051df  test    eax, eax
0x1800051e1  jz      loc_180005307
0x1800051e7  movaps  xmm0, [rsp+270h+var_230]
0x1800051ec  lea     r8, [rbp+170h+var_130]
0x1800051f0  movaps  xmm1, [rsp+270h+var_220]
0x1800051f5  lea     rdx, [rsp+270h+var_240]
0x1800051fa  mov     rax, [rbp+170h+var_140]
0x1800051fe  mov     rcx, [rdi+0F0h]
0x180005205  movups  [rbp+170h+var_130], xmm0
0x180005209  mov     [rbp+170h+var_40], rax
0x180005210  movaps  xmm0, [rsp+270h+var_210]
0x180005215  movups  [rbp+170h+var_110], xmm0
0x180005219  movaps  xmm0, [rbp+170h+var_1F0]
0x18000521d  movups  [rbp+170h+var_F0], xmm0
0x180005224  movaps  xmm0, [rbp+170h+var_1D0]
0x180005228  movups  [rbp+170h+var_120], xmm1
0x18000522c  movaps  xmm1, [rsp+270h+var_200]
0x180005231  movups  [rbp+170h+var_D0], xmm0
0x180005238  movaps  xmm0, [rbp+170h+var_1B0]
0x18000523c  movups  [rbp+170h+var_100], xmm1
0x180005240  movaps  xmm1, [rbp+170h+var_1E0]
0x180005244  movups  [rbp+170h+var_B0], xmm0
0x18000524b  movaps  xmm0, [rbp+170h+var_190]
0x18000524f  movups  [rbp+170h+var_E0], xmm1
0x180005256  movaps  xmm1, [rbp+170h+var_1C0]
0x18000525a  movups  [rbp+170h+var_90], xmm0
0x180005261  movaps  xmm0, [rbp+170h+var_170]
0x180005265  movups  [rbp+170h+var_C0], xmm1
0x18000526c  movaps  xmm1, [rbp+170h+var_1A0]
0x180005270  movups  [rbp+170h+var_70], xmm0
0x180005277  movaps  xmm0, [rbp+170h+var_150]
0x18000527b  movups  [rbp+170h+var_A0], xmm1
0x180005282  movaps  xmm1, [rbp+170h+var_180]
0x180005286  movups  [rbp+170h+var_50], xmm0
0x18000528d  movups  xmm0, xmmword ptr [rdi+134h]
0x180005294  movups  [rbp+170h+var_80], xmm1
0x18000529b  movaps  xmm1, [rbp+170h+var_160]
0x18000529f  movaps  [rsp+270h+var_240], xmm0
0x1800052a4  movups  [rbp+170h+var_60], xmm1
0x1800052ab  call    cs:__imp_TbUpdateEvent
0x1800052b1  mov     edi, eax
0x1800052b3  test    eax, eax
0x1800052b5  jnz     loc_1800053BB
0x1800052bb  xor     edx, edx; Token
0x1800052bd  xor     ecx, ecx; Thread
0x1800052bf  call    cs:__imp_SetThreadToken
0x1800052c5  test    eax, eax
0x1800052c7  jz      loc_1800053FC
0x1800052cd  mov     rcx, rbx; lpCriticalSection
0x1800052d0  call    cs:__imp_EnterCriticalSection
0x1800052d6  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800052dd  jnz     short loc_180005346
0x1800052df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052e6  cmp     rcx, r15
0x1800052e9  jz      short loc_1800052F5
0x1800052eb  test    byte ptr [rcx+1Ch], 1
0x1800052ef  jnz     loc_18000545D
0x1800052f5  mov     eax, edi
0x1800052f7  add     rsp, 248h
0x1800052fe  pop     r15
0x180005300  pop     r14
0x180005302  pop     rdi
0x180005303  pop     rsi
0x180005304  pop     rbx
0x180005305  pop     rbp
0x180005306  retn
0x180005307  call    cs:__imp_GetLastError
0x18000530d  mov     edi, eax
0x18000530f  jmp     short loc_1800052CD
0x180005311  test    byte ptr [rbx+1Ch], 1
0x180005315  jz      loc_180005152
0x18000531b  cmp     byte ptr [rbx+19h], 6
0x18000531f  jb      loc_180005152
0x180005325  mov     rcx, [rbx+10h]
0x180005329  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180005330  mov     edx, 43h ; 'C'
0x180005335  call    WPP_SF_
0x18000533a  mov     rbx, cs:WPP_GLOBAL_Control
0x180005341  jmp     loc_180005152
0x180005346  mov     r9d, edi
0x180005349  lea     r8, aKamKampupdatet; "Kam:KampUpdateTimeEventHelper finished"
0x180005350  call    McTemplateU0zq_EventWriteTransfer
0x180005355  jmp     short loc_1800052DF
0x180005357  cmp     byte ptr [rbx+19h], 6
0x18000535b  jb      loc_180005181
0x180005361  mov     rcx, [rbx+10h]
0x180005365  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x18000536c  test    r14d, r14d
0x18000536f  mov     edx, 28h ; '('
0x180005374  mov     r9d, esi
0x180005377  setnz   al
0x18000537a  mov     [rsp+270h+var_250], al
0x18000537e  call    WPP_SF_dc
0x180005383  mov     rbx, cs:WPP_GLOBAL_Control
0x18000538a  jmp     loc_180005181
0x18000538f  cmp     byte ptr [rbx+19h], 6
0x180005393  jb      loc_1800051C3
0x180005399  mov     rcx, [rbx+10h]
0x18000539d  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800053a4  mov     edx, 29h ; ')'
0x1800053a9  mov     dword ptr [rsp+270h+var_250], 3Ch ; '<'
0x1800053b1  call    WPP_SF_dd
0x1800053b6  jmp     loc_1800051C3
0x1800053bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053c2  cmp     rcx, r15
0x1800053c5  jz      loc_1800052BB
0x1800053cb  test    byte ptr [rcx+1Ch], 1
0x1800053cf  jz      loc_1800052BB
0x1800053d5  cmp     byte ptr [rcx+19h], 3
0x1800053d9  jb      loc_1800052BB
0x1800053df  mov     rcx, [rcx+10h]
0x1800053e3  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800053ea  mov     edx, 44h ; 'D'
0x1800053ef  mov     r9d, eax
0x1800053f2  call    WPP_SF_d
0x1800053f7  jmp     loc_1800052BB
0x1800053fc  call    cs:__imp_GetLastError
0x180005402  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180005409  mov     edi, eax
0x18000540b  jz      short loc_18000541C
0x18000540d  mov     r9d, eax
0x180005410  lea     r8, aKamKampupdatet_1; "Kam:KampUpdateTimeEventHelper failed to"...
0x180005417  call    McTemplateU0zq_EventWriteTransfer
0x18000541c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005423  cmp     rcx, r15
0x180005426  jz      loc_1800052CD
0x18000542c  test    byte ptr [rcx+1Ch], 1
0x180005430  jz      loc_1800052CD
0x180005436  cmp     byte ptr [rcx+19h], 2
0x18000543a  jb      loc_1800052CD
0x180005440  mov     rcx, [rcx+10h]
0x180005444  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x18000544b  mov     edx, 45h ; 'E'
0x180005450  mov     r9d, edi
0x180005453  call    WPP_SF_d
0x180005458  jmp     loc_1800052CD
0x18000545d  cmp     byte ptr [rcx+19h], 6
0x180005461  jb      loc_1800052F5
0x180005467  mov     rcx, [rcx+10h]
0x18000546b  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180005472  mov     edx, 46h ; 'F'
0x180005477  mov     r9d, edi
0x18000547a  call    WPP_SF_d
0x18000547f  jmp     loc_1800052F5
```
