# PlaServer

- ea: `0x18010dea0`
- end: `0x18010e332`
- name: `PlaServer`
- size: `1170`
- prototype: `void()`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18000d8c0`
- `0x18010dea0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18010dff3`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18010dff3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18010ded1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18010ded1`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18010e165`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18010e165`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18010e1b2`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18010e1b2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18010e1ca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18010e1ca`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010e182`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010e182`

## pseudocode

```c
void PlaServer()
{
  HRESULT v0; // eax
  struct _PLA_OBJECT near **v1; // r15
  __int64 v2; // rdi
  int v3; // ebx
  __int64 v4; // rdi
  HRESULT v5; // eax
  unsigned __int16 *v6; // rax
  IUnknown *v7; // rsi
  struct _PLA_OBJECT near **v8; // r14
  const IID *v9; // rax
  HRESULT v10; // eax
  int v11; // [rsp+70h] [rbp-90h] BYREF
  HRESULT v12; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v13[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v14[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v15[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v16[64]; // [rsp+200h] [rbp+100h] BYREF

  v0 = CoInitializeEx(0, 0);
  v1 = &g_PlaObjects;
  if ( v0 >= 0 )
  {
    v4 = -1;
    v5 = CoInitializeSecurity(0, -1, 0, 0, 6u, 3u, 0, 0x2020u, 0);
    if ( v5 >= 0 )
    {
      v7 = 0;
      v8 = &g_PlaObjects;
      v3 = 1;
      if ( off_180167010 )
      {
        while ( 1 )
        {
          if ( v7 )
            ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
          v7 = (IUnknown *)operator new(0x20u, qword_180147320, 0);
          if ( !v7 )
            break;
          v9 = (const IID *)*v8;
          v7->lpVtbl = (struct IUnknownVtbl *)&CClassFactory::`vftable';
          LODWORD(v7[1].lpVtbl) = 1;
          *(IID *)((char *)&v7[1].lpVtbl + 4) = *v9;
          _InterlockedAdd(&g_Count, 1u);
          v10 = CoRegisterClassObject((const IID *const)*v8, v7, 0x15u, 1u, (LPDWORD)v8 + 2);
          if ( v10 < 0 )
          {
            v12 = 0;
            v11 = v10;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v15, 0x4000000000000800uLL);
              do
                ++v4;
              while ( v15[v4] );
              EventingWriteEvent(
                &g_Eventing,
                PLA_EVENT_ERROR,
                5,
                &v11,
                4,
                qword_180147320,
                1,
                &v12,
                4,
                "PlaServer",
                10,
                v15,
                (unsigned int)(2 * v4) + 2LL);
            }
            goto LABEL_26;
          }
          v8 += 3;
          if ( !v8[2] )
            goto LABEL_24;
        }
        v12 = 0;
        v11 = -2147024882;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v16, 0x4000000000000800uLL);
          do
            ++v4;
          while ( v16[v4] );
          v6 = v16;
          goto LABEL_16;
        }
      }
      else
      {
        do
LABEL_24:
          Sleep(0x2BF20u);
        while ( g_Count > 0 );
        if ( v7 )
LABEL_26:
          ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
      }
    }
    else
    {
      v12 = 0;
      v11 = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v14, 0x4000000000000800uLL);
        do
          ++v4;
        while ( v14[v4] );
        v6 = v14;
        v3 = 1;
LABEL_16:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v11,
          4,
          qword_180147320,
          1,
          &v12,
          4,
          "PlaServer",
          10,
          v6,
          (unsigned int)(2 * v4) + 2LL);
      }
      else
      {
        v3 = 1;
      }
    }
  }
  else
  {
    v11 = 0;
    v12 = v0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v13, 0x4000000000000800uLL);
      v2 = -1;
      do
        ++v2;
      while ( v13[v2] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v12,
        4,
        qword_180147320,
        1,
        &v11,
        4,
        "PlaServer",
        10,
        v13,
        (unsigned int)(2 * v2) + 2LL);
    }
    v3 = 0;
  }
  if ( off_180167010 )
  {
    do
    {
      CoRevokeClassObject(*((_DWORD *)v1 + 2));
      *((_DWORD *)v1 + 2) = 0;
      v1 += 3;
    }
    while ( v1[2] );
  }
  if ( v3 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18010dea0  push    rbp
0x18010dea2  push    rbx
0x18010dea3  push    rsi
0x18010dea4  push    rdi
0x18010dea5  push    r12
0x18010dea7  push    r13
0x18010dea9  push    r14
0x18010deab  push    r15
0x18010dead  lea     rbp, [rsp-198h]
0x18010deb5  sub     rsp, 298h
0x18010debc  mov     rax, cs:__security_cookie
0x18010dec3  xor     rax, rsp
0x18010dec6  mov     [rbp+1D0h+var_50], rax
0x18010decd  xor     edx, edx; dwCoInit
0x18010decf  xor     ecx, ecx; pvReserved
0x18010ded1  call    cs:__imp_CoInitializeEx
0x18010ded7  xor     r13d, r13d
0x18010deda  lea     r15, ?g_PlaObjects@@3PAU_PLA_OBJECT@@A; _PLA_OBJECT near * g_PlaObjects
0x18010dee1  test    eax, eax
0x18010dee3  jns     loc_18010DFC3
0x18010dee9  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010def0  mov     [rsp+2D0h+var_260], r13d
0x18010def5  mov     [rsp+2D0h+var_258], eax
0x18010def9  jz      loc_18010DFBB
0x18010deff  mov     rdx, 4000000000000800h; unsigned __int64
0x18010df09  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010df10  jz      loc_18010DFBB
0x18010df16  mov     rax, cs:qword_180169748
0x18010df1d  and     rax, rdx
0x18010df20  cmp     cs:qword_180169748, rax
0x18010df27  jnz     loc_18010DFBB
0x18010df2d  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18010df31  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010df36  lea     rax, [rbp+1D0h+var_250]
0x18010df3a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010df3e  inc     rdi
0x18010df41  cmp     [rax+rdi*2], r13w
0x18010df46  jnz     short loc_18010DF3E
0x18010df48  lea     rax, [rbp+1D0h+var_250]
0x18010df4c  lea     ecx, [rdi+rdi]
0x18010df4f  add     rcx, 2
0x18010df53  lea     r12, qword_180147320
0x18010df5a  mov     [rsp+2D0h+var_270], rcx
0x18010df5f  lea     r9, [rsp+2D0h+var_258]
0x18010df64  mov     [rsp+2D0h+var_278], rax
0x18010df69  lea     rcx, [rsp+2D0h+var_260]
0x18010df6e  mov     [rsp+2D0h+var_280], 0Ah
0x18010df77  lea     rax, aPlaserver_0; "PlaServer"
0x18010df7e  mov     [rsp+2D0h+var_288], rax
0x18010df83  lea     rdx, PLA_EVENT_ERROR
0x18010df8a  mov     eax, 4
0x18010df8f  mov     [rsp+2D0h+pReserved3], rax
0x18010df94  mov     qword ptr [rsp+2D0h+dwCapabilities], rcx
0x18010df99  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18010dfa0  lea     ebx, [rax-3]
0x18010dfa3  mov     [rsp+2D0h+pAuthList], rbx
0x18010dfa8  lea     r8d, [rax+1]
0x18010dfac  mov     qword ptr [rsp+2D0h+dwImpLevel], r12
0x18010dfb1  mov     qword ptr [rsp+2D0h+dwAuthnLevel], rax
0x18010dfb6  call    EventingWriteEvent
0x18010dfbb  mov     ebx, r13d
0x18010dfbe  jmp     loc_18010E1A5
0x18010dfc3  mov     [rsp+2D0h+pReserved3], r13; pReserved3
0x18010dfc8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010dfcc  mov     [rsp+2D0h+dwCapabilities], 2020h; dwCapabilities
0x18010dfd4  xor     r9d, r9d; pReserved1
0x18010dfd7  mov     [rsp+2D0h+pAuthList], r13; pAuthList
0x18010dfdc  xor     r8d, r8d; asAuthSvc
0x18010dfdf  mov     [rsp+2D0h+dwImpLevel], 3; dwImpLevel
0x18010dfe7  mov     edx, edi; cAuthSvc
0x18010dfe9  xor     ecx, ecx; pSecDesc
0x18010dfeb  mov     [rsp+2D0h+dwAuthnLevel], 6; dwAuthnLevel
0x18010dff3  call    cs:__imp_CoInitializeSecurity
0x18010dff9  test    eax, eax
0x18010dffb  jns     loc_18010E0E0
0x18010e001  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e008  mov     [rsp+2D0h+var_258], r13d
0x18010e00d  mov     [rsp+2D0h+var_260], eax
0x18010e011  jz      loc_18010E0D6
0x18010e017  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e021  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e028  jz      loc_18010E0D6
0x18010e02e  mov     rax, cs:qword_180169748
0x18010e035  and     rax, rdx
0x18010e038  cmp     cs:qword_180169748, rax
0x18010e03f  jnz     loc_18010E0D6
0x18010e045  lea     rcx, [rbp+1D0h+var_1D0]; unsigned __int16 *
0x18010e049  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e04e  lea     rax, [rbp+1D0h+var_1D0]
0x18010e052  inc     rdi
0x18010e055  cmp     [rax+rdi*2], r13w
0x18010e05a  jnz     short loc_18010E052
0x18010e05c  lea     rax, [rbp+1D0h+var_1D0]
0x18010e060  mov     ebx, 1
0x18010e065  lea     r12, qword_180147320
0x18010e06c  lea     ecx, [rdi+rdi]
0x18010e06f  add     rcx, 2
0x18010e073  lea     r9, [rsp+2D0h+var_260]
0x18010e078  mov     [rsp+2D0h+var_270], rcx
0x18010e07d  lea     rdx, PLA_EVENT_ERROR
0x18010e084  mov     [rsp+2D0h+var_278], rax
0x18010e089  lea     rcx, [rsp+2D0h+var_258]
0x18010e08e  mov     [rsp+2D0h+var_280], 0Ah
0x18010e097  lea     rax, aPlaserver_0; "PlaServer"
0x18010e09e  mov     [rsp+2D0h+var_288], rax
0x18010e0a3  mov     eax, 4
0x18010e0a8  mov     [rsp+2D0h+pReserved3], rax
0x18010e0ad  mov     qword ptr [rsp+2D0h+dwCapabilities], rcx
0x18010e0b2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18010e0b9  mov     [rsp+2D0h+pAuthList], rbx
0x18010e0be  mov     qword ptr [rsp+2D0h+dwImpLevel], r12
0x18010e0c3  lea     r8d, [rax+1]
0x18010e0c7  mov     qword ptr [rsp+2D0h+dwAuthnLevel], rax
0x18010e0cc  call    EventingWriteEvent
0x18010e0d1  jmp     loc_18010E1A5
0x18010e0d6  mov     ebx, 1
0x18010e0db  jmp     loc_18010E1A5
0x18010e0e0  cmp     cs:off_180167010, r13
0x18010e0e7  mov     rsi, r13
0x18010e0ea  mov     r14, r15
0x18010e0ed  mov     ebx, 1
0x18010e0f2  jz      loc_18010E17D
0x18010e0f8  lea     r12, qword_180147320
0x18010e0ff  test    rsi, rsi
0x18010e102  jz      short loc_18010E113
0x18010e104  mov     rax, [rsi]
0x18010e107  mov     rcx, rsi
0x18010e10a  mov     rax, [rax+10h]
0x18010e10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e113  xor     r8d, r8d; int
0x18010e116  mov     rdx, r12; char *
0x18010e119  lea     ecx, [r8+20h]; dwBytes
0x18010e11d  call    ??2@YAPEAX_KPEBDH@Z; operator new(unsigned __int64,char const *,int)
0x18010e122  mov     rsi, rax
0x18010e125  test    rax, rax
0x18010e128  jz      loc_18010E2C1
0x18010e12e  mov     rax, [r14]
0x18010e131  lea     rcx, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x18010e138  mov     [rsi], rcx
0x18010e13b  mov     [rsi+8], ebx
0x18010e13e  movups  xmm0, xmmword ptr [rax]
0x18010e141  movdqu  xmmword ptr [rsi+0Ch], xmm0
0x18010e146  lock add cs:?g_Count@@3JA, ebx; long g_Count
0x18010e14d  mov     rcx, [r14]; rclsid
0x18010e150  lea     rax, [r14+8]
0x18010e154  mov     r9d, ebx; flags
0x18010e157  mov     qword ptr [rsp+2D0h+dwAuthnLevel], rax; lpdwRegister
0x18010e15c  mov     r8d, 15h; dwClsContext
0x18010e162  mov     rdx, rsi; pUnk
0x18010e165  call    cs:__imp_CoRegisterClassObject
0x18010e16b  test    eax, eax
0x18010e16d  js      loc_18010E1F3
0x18010e173  add     r14, 18h
0x18010e177  cmp     [r14+10h], r13
0x18010e17b  jnz     short loc_18010E0FF
0x18010e17d  mov     ecx, 2BF20h; dwMilliseconds
0x18010e182  call    cs:__imp_Sleep
0x18010e188  cmp     cs:?g_Count@@3JA, r13d; long g_Count
0x18010e18f  jg      short loc_18010E17D
0x18010e191  test    rsi, rsi
0x18010e194  jz      short loc_18010E1A5
0x18010e196  mov     rax, [rsi]
0x18010e199  mov     rcx, rsi
0x18010e19c  mov     rax, [rax+10h]
0x18010e1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e1a5  cmp     cs:off_180167010, r13
0x18010e1ac  jz      short loc_18010E1C6
0x18010e1ae  mov     ecx, [r15+8]; dwRegister
0x18010e1b2  call    cs:__imp_CoRevokeClassObject
0x18010e1b8  mov     [r15+8], r13d
0x18010e1bc  lea     r15, [r15+18h]
0x18010e1c0  cmp     [r15+10h], r13
0x18010e1c4  jnz     short loc_18010E1AE
0x18010e1c6  test    ebx, ebx
0x18010e1c8  jz      short loc_18010E1D0
0x18010e1ca  call    cs:__imp_CoUninitialize
0x18010e1d0  mov     rcx, [rbp+1D0h+var_50]
0x18010e1d7  xor     rcx, rsp; StackCookie
0x18010e1da  call    __security_check_cookie
0x18010e1df  add     rsp, 298h
0x18010e1e6  pop     r15
0x18010e1e8  pop     r14
0x18010e1ea  pop     r13
0x18010e1ec  pop     r12
0x18010e1ee  pop     rdi
0x18010e1ef  pop     rsi
0x18010e1f0  pop     rbx
0x18010e1f1  pop     rbp
0x18010e1f2  retn
0x18010e1f3  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e1fa  mov     [rsp+2D0h+var_258], r13d
0x18010e1ff  mov     [rsp+2D0h+var_260], eax
0x18010e203  jz      short loc_18010E196
0x18010e205  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e20f  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e216  jz      loc_18010E196
0x18010e21c  mov     rax, cs:qword_180169748
0x18010e223  and     rax, rdx
0x18010e226  cmp     cs:qword_180169748, rax
0x18010e22d  jnz     loc_18010E196
0x18010e233  lea     rcx, [rbp+1D0h+var_150]; unsigned __int16 *
0x18010e23a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e23f  lea     rax, [rbp+1D0h+var_150]
0x18010e246  inc     rdi
0x18010e249  cmp     [rax+rdi*2], r13w
0x18010e24e  jnz     short loc_18010E246
0x18010e250  lea     rax, [rbp+1D0h+var_150]
0x18010e257  lea     ecx, [rdi+rdi]
0x18010e25a  add     rcx, 2
0x18010e25e  lea     r9, [rsp+2D0h+var_260]
0x18010e263  mov     [rsp+2D0h+var_270], rcx
0x18010e268  lea     rdx, PLA_EVENT_ERROR
0x18010e26f  mov     [rsp+2D0h+var_278], rax
0x18010e274  lea     rcx, [rsp+2D0h+var_258]
0x18010e279  mov     [rsp+2D0h+var_280], 0Ah
0x18010e282  lea     rax, aPlaserver_0; "PlaServer"
0x18010e289  mov     [rsp+2D0h+var_288], rax
0x18010e28e  mov     eax, 4
0x18010e293  mov     [rsp+2D0h+pReserved3], rax
0x18010e298  mov     qword ptr [rsp+2D0h+dwCapabilities], rcx
0x18010e29d  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18010e2a4  mov     [rsp+2D0h+pAuthList], rbx
0x18010e2a9  mov     qword ptr [rsp+2D0h+dwImpLevel], r12
0x18010e2ae  lea     r8d, [rax+1]
0x18010e2b2  mov     qword ptr [rsp+2D0h+dwAuthnLevel], rax
0x18010e2b7  call    EventingWriteEvent
0x18010e2bc  jmp     loc_18010E196
0x18010e2c1  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010e2c8  mov     [rsp+2D0h+var_258], r13d
0x18010e2cd  mov     [rsp+2D0h+var_260], 8007000Eh
0x18010e2d5  jz      loc_18010E1A5
0x18010e2db  mov     rdx, 4000000000000800h; unsigned __int64
0x18010e2e5  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010e2ec  jz      loc_18010E1A5
0x18010e2f2  mov     rax, cs:qword_180169748
0x18010e2f9  and     rax, rdx
0x18010e2fc  cmp     cs:qword_180169748, rax
0x18010e303  jnz     loc_18010E1A5
0x18010e309  lea     rcx, [rbp+1D0h+var_D0]; unsigned __int16 *
0x18010e310  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010e315  lea     rax, [rbp+1D0h+var_D0]
0x18010e31c  inc     rdi
0x18010e31f  cmp     [rax+rdi*2], r13w
0x18010e324  jnz     short loc_18010E31C
0x18010e326  lea     rax, [rbp+1D0h+var_D0]
0x18010e32d  jmp     loc_18010E06C
```
