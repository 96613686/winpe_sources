# BindInterfaceInAllProtocols

- ea: `0x180015550`
- end: `0x180015975`
- name: `BindInterfaceInAllProtocols`
- size: `1061`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016f34`
- `0x180018be4`
- `0x1800292bc`

## callees

- `0x180011790`
- `0x180015550`
- `0x18001597c`
- `0x18001bbf4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001594b`
- `ntdll!RtlReleaseResource` at `0x18001594b`
- `ntdll!RtlAcquireResourceShared` at `0x180015885`
- `ntdll!RtlAcquireResourceShared` at `0x180015885`
- `KERNEL32!HeapFree` at `0x18001593e`
- `KERNEL32!HeapFree` at `0x18001593e`
- `KERNEL32!HeapAlloc` at `0x180015726`
- `KERNEL32!HeapAlloc` at `0x180015726`

## string_xrefs

- `0x1800155e3`: `Entered: BindInterfaceInAllProtocols`
- `0x180015626`: `BindInterfaceInAllProtocols: Not binding %ws since no addresses present`
- `0x1800156b0`: `BindInterfaceInAllProtocols: Arithmetic overflow error allocating %d bytes for bindings`
- `0x180015742`: `BindInterfaceInAllProtocols: Error allocating %d bytes for bindings`
- `0x1800158bb`: `BindInterfaceInAllProtocols: Couldnt bind interface %ws to %ws. Error %d`

## pseudocode

```c
__int64 __fastcall BindInterfaceInAllProtocols(__int64 a1)
{
  unsigned int v1; // esi
  char v3; // r11
  __int128 *v4; // r9
  __int64 v5; // r8
  __int128 *v6; // r9
  int v8; // eax
  char v9; // r11
  unsigned __int16 v10; // di
  __int128 *v11; // r9
  char *v12; // rax
  void *v13; // rdi
  __int128 *v14; // r9
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  unsigned int v19; // r14d
  _QWORD *i; // rsi
  int v21; // eax
  __int64 v22; // r8
  __int128 *v23; // r9
  __int64 v24; // [rsp+20h] [rbp-898h]
  SIZE_T dwBytes; // [rsp+30h] [rbp-888h] BYREF
  __int128 v26; // [rsp+38h] [rbp-880h] BYREF
  int v27; // [rsp+48h] [rbp-870h] BYREF
  __int128 v28; // [rsp+4Ch] [rbp-86Ch]
  __int128 v29; // [rsp+5Ch] [rbp-85Ch]
  int v30; // [rsp+6Ch] [rbp-84Ch]
  int v31; // [rsp+70h] [rbp-848h] BYREF
  _BYTE v32[2044]; // [rsp+74h] [rbp-844h] BYREF

  v1 = *(_DWORD *)(a1 + 516);
  LODWORD(dwBytes) = 0;
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v3 = Microsoft_Windows_RRASEnableBits;
  v27 = 0;
  v30 = 0;
  v28 = 0;
  v29 = 0;
  v26 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v27) = 0;
    v4 = &v26;
    if ( a1 != -688 )
      LODWORD(v4) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: BindInterfaceInAllProtocols",
      (_DWORD)v4,
      *(_QWORD *)(a1 + 72),
      (__int64)&v27);
    v3 = Microsoft_Windows_RRASEnableBits;
  }
  if ( *(_DWORD *)(a1 + 512) )
  {
    v8 = SizeofIpBinding(*(unsigned int *)(a1 + 668), v1, &dwBytes);
    v10 = v8;
    if ( v8 >= 0 )
    {
      v12 = (char *)HeapAlloc(IPRouterHeap, 0, (unsigned int)dwBytes);
      v13 = v12;
      if ( v12 )
      {
        v15 = 0;
        *(_DWORD *)v12 = *(_DWORD *)(a1 + 668);
        if ( v1 )
        {
          *((_DWORD *)v12 + 1) = *(_DWORD *)(a1 + 672);
          *((_DWORD *)v12 + 2) = *(_DWORD *)(a1 + 532);
          *((_QWORD *)v12 + 2) = *(_QWORD *)(a1 + 536);
          if ( *(_DWORD *)(a1 + 668) )
          {
            do
            {
              v16 = 28LL * (unsigned int)v15;
              *(_DWORD *)&v12[8 * v15 + 24] = *(_DWORD *)(v16 + *(_QWORD *)(a1 + 712));
              *(_DWORD *)&v12[8 * v15 + 28] = *(_DWORD *)(*(_QWORD *)(a1 + 712) + v16 + 4);
              v15 = (unsigned int)(v15 + 1);
            }
            while ( (unsigned int)v15 < *(_DWORD *)(a1 + 668) );
          }
        }
        else
        {
          *(_OWORD *)(v12 + 4) = *(_OWORD *)(a1 + 672);
          *((_DWORD *)v12 + 5) = *(_DWORD *)(a1 + 532);
          *((_QWORD *)v12 + 3) = *(_QWORD *)(a1 + 536);
          if ( *(_DWORD *)(a1 + 668) )
          {
            do
            {
              v17 = 5 * v15;
              v18 = 28LL * (unsigned int)v15;
              v15 = (unsigned int)(v15 + 1);
              *(_OWORD *)&v12[4 * v17 + 32] = *(_OWORD *)(v18 + *(_QWORD *)(a1 + 712) + 4);
              *(_DWORD *)&v12[4 * v17 + 48] = *(_DWORD *)(v18 + *(_QWORD *)(a1 + 712));
            }
            while ( (unsigned int)v15 < *(_DWORD *)(a1 + 668) );
          }
        }
        v19 = 0;
        RtlAcquireResourceShared(&stru_18008C4A0, 1u);
        for ( i = *(_QWORD **)(a1 + 56); i != (_QWORD *)(a1 + 56); i = (_QWORD *)*i )
        {
          v21 = BindInterfaceInProtocol(a1, i[3], v13);
          if ( v21 )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v22 = *(_QWORD *)(a1 + 72);
              LODWORD(v24) = v21;
              LOWORD(v31) = 0;
              LOWORD(v27) = 0;
              FormatRRASErrorString(
                &v31,
                L"BindInterfaceInAllProtocols: Couldnt bind interface %ws to %ws. Error %d",
                v22,
                *(_QWORD *)(i[3] + 32LL),
                v24);
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                v23 = &v26;
                if ( a1 != -688 )
                  LODWORD(v23) = a1 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrMgrParamTraceError,
                  (unsigned int)&v31,
                  (_DWORD)v23,
                  *(_QWORD *)(a1 + 72),
                  (__int64)&v27);
              }
            }
            v19 = 1003;
          }
        }
        HeapFree(IPRouterHeap, 0, v13);
        RtlReleaseResource(&stru_18008C4A0);
        return v19;
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v31) = 0;
          LOWORD(v27) = 0;
          FormatRRASErrorString(
            &v31,
            L"BindInterfaceInAllProtocols: Error allocating %d bytes for bindings",
            (unsigned int)dwBytes);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v14 = &v26;
            if ( a1 != -688 )
              LODWORD(v14) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v31,
              (_DWORD)v14,
              *(_QWORD *)(a1 + 72),
              (__int64)&v27);
          }
        }
        return 8;
      }
    }
    else
    {
      if ( (v9 & 0x40) != 0 )
      {
        LOWORD(v31) = 0;
        LOWORD(v27) = 0;
        FormatRRASErrorString(
          &v31,
          L"BindInterfaceInAllProtocols: Arithmetic overflow error allocating %d bytes for bindings",
          (unsigned int)dwBytes);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v11 = &v26;
          if ( a1 != -688 )
            LODWORD(v11) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v31,
            (_DWORD)v11,
            *(_QWORD *)(a1 + 72),
            (__int64)&v27);
        }
      }
      return v10;
    }
  }
  else
  {
    if ( v3 < 0 )
    {
      v5 = *(_QWORD *)(a1 + 72);
      LOWORD(v31) = 0;
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v31, L"BindInterfaceInAllProtocols: Not binding %ws since no addresses present", v5);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v6 = &v26;
        if ( a1 != -688 )
          LODWORD(v6) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v31,
          (_DWORD)v6,
          *(_QWORD *)(a1 + 72),
          (__int64)&v27);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180015550  push    rbx
0x180015552  push    rsi
0x180015553  push    rdi
0x180015554  push    r13
0x180015556  push    r14
0x180015558  push    r15
0x18001555a  sub     rsp, 888h
0x180015561  mov     rax, cs:__security_cookie
0x180015568  xor     rax, rsp
0x18001556b  mov     [rsp+8B8h+var_48], rax
0x180015573  mov     esi, [rcx+204h]
0x180015579  mov     rbx, rcx
0x18001557c  xor     eax, eax
0x18001557e  mov     dword ptr [rsp+8B8h+dwBytes], 0
0x180015586  lea     rcx, [rsp+8B8h+var_844]; void *
0x18001558b  mov     [rsp+8B8h+var_848], eax
0x18001558f  xor     edx, edx; Val
0x180015591  mov     r8d, 7FCh; Size
0x180015597  call    memset_0
0x18001559c  mov     r11, cs:Microsoft_Windows_RRASEnableBits
0x1800155a3  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800155aa  xor     eax, eax
0x1800155ac  xorps   xmm0, xmm0
0x1800155af  mov     [rsp+8B8h+var_870], eax
0x1800155b3  mov     [rsp+8B8h+var_84C], eax
0x1800155b7  movups  [rsp+8B8h+var_86C], xmm0
0x1800155bc  movups  [rsp+8B8h+var_85C], xmm0
0x1800155c1  movups  [rsp+8B8h+var_880], xmm0
0x1800155c6  test    r11b, 80h
0x1800155ca  jz      short loc_180015614
0x1800155cc  mov     word ptr [rsp+8B8h+var_870], ax
0x1800155d1  lea     r9, [rsp+8B8h+var_880]
0x1800155d6  lea     rax, [rbx+2B0h]
0x1800155dd  mov     rcx, r13
0x1800155e0  test    rax, rax
0x1800155e3  lea     r8, aEnteredBindint; "Entered: BindInterfaceInAllProtocols"
0x1800155ea  lea     rdx, RasRtrmgrParamTraceInfo
0x1800155f1  cmovnz  r9, rax
0x1800155f5  lea     rax, [rsp+8B8h+var_870]
0x1800155fa  mov     [rsp+8B8h+var_890], rax
0x1800155ff  mov     rax, [rbx+48h]
0x180015603  mov     [rsp+8B8h+var_898], rax
0x180015608  call    McTemplateU0zjzz_EventWriteTransfer
0x18001560d  mov     r11, cs:Microsoft_Windows_RRASEnableBits
0x180015614  cmp     dword ptr [rbx+200h], 0
0x18001561b  jnz     short loc_18001568D
0x18001561d  test    r11b, r11b
0x180015620  jns     short loc_180015686
0x180015622  mov     r8, [rbx+48h]
0x180015626  lea     rdx, aBindinterfacei_4; "BindInterfaceInAllProtocols: Not bindin"...
0x18001562d  xor     eax, eax
0x18001562f  lea     rcx, [rsp+8B8h+var_848]
0x180015634  mov     word ptr [rsp+8B8h+var_848], ax
0x180015639  mov     word ptr [rsp+8B8h+var_870], ax
0x18001563e  call    FormatRRASErrorString
0x180015643  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001564a  jge     short loc_180015686
0x18001564c  lea     rax, [rbx+2B0h]
0x180015653  mov     rcx, r13
0x180015656  test    rax, rax
0x180015659  lea     r9, [rsp+8B8h+var_880]
0x18001565e  lea     r8, [rsp+8B8h+var_848]
0x180015663  cmovnz  r9, rax
0x180015667  lea     rdx, RasRtrmgrParamTraceInfo
0x18001566e  lea     rax, [rsp+8B8h+var_870]
0x180015673  mov     [rsp+8B8h+var_890], rax
0x180015678  mov     rax, [rbx+48h]
0x18001567c  mov     [rsp+8B8h+var_898], rax
0x180015681  call    McTemplateU0zjzz_EventWriteTransfer
0x180015686  xor     eax, eax
0x180015688  jmp     loc_180015954
0x18001568d  mov     ecx, [rbx+29Ch]
0x180015693  lea     r8, [rsp+8B8h+dwBytes]
0x180015698  mov     edx, esi
0x18001569a  call    SizeofIpBinding
0x18001569f  mov     edi, eax
0x1800156a1  test    eax, eax
0x1800156a3  jns     short loc_180015718
0x1800156a5  test    r11b, 40h
0x1800156a9  jz      short loc_180015710
0x1800156ab  mov     r8d, dword ptr [rsp+8B8h+dwBytes]
0x1800156b0  lea     rdx, aBindinterfacei; "BindInterfaceInAllProtocols: Arithmetic"...
0x1800156b7  xor     ecx, ecx
0x1800156b9  mov     word ptr [rsp+8B8h+var_848], cx
0x1800156be  mov     word ptr [rsp+8B8h+var_870], cx
0x1800156c3  lea     rcx, [rsp+8B8h+var_848]
0x1800156c8  call    FormatRRASErrorString
0x1800156cd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800156d4  jz      short loc_180015710
0x1800156d6  lea     rax, [rbx+2B0h]
0x1800156dd  mov     rcx, r13
0x1800156e0  test    rax, rax
0x1800156e3  lea     r9, [rsp+8B8h+var_880]
0x1800156e8  lea     r8, [rsp+8B8h+var_848]
0x1800156ed  cmovnz  r9, rax
0x1800156f1  lea     rdx, RasRtrMgrParamTraceError
0x1800156f8  lea     rax, [rsp+8B8h+var_870]
0x1800156fd  mov     [rsp+8B8h+var_890], rax
0x180015702  mov     rax, [rbx+48h]
0x180015706  mov     [rsp+8B8h+var_898], rax
0x18001570b  call    McTemplateU0zjzz_EventWriteTransfer
0x180015710  movzx   eax, di
0x180015713  jmp     loc_180015954
0x180015718  mov     r8d, dword ptr [rsp+8B8h+dwBytes]; dwBytes
0x18001571d  xor     edx, edx; dwFlags
0x18001571f  mov     rcx, cs:IPRouterHeap; hHeap
0x180015726  call    cs:__imp_HeapAlloc
0x18001572c  mov     rdi, rax
0x18001572f  test    rax, rax
0x180015732  jnz     short loc_1800157AA
0x180015734  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001573b  jz      short loc_1800157A0
0x18001573d  mov     r8d, dword ptr [rsp+8B8h+dwBytes]
0x180015742  lea     rdx, aBindinterfacei_3; "BindInterfaceInAllProtocols: Error allo"...
0x180015749  lea     rcx, [rsp+8B8h+var_848]
0x18001574e  mov     word ptr [rsp+8B8h+var_848], ax
0x180015753  mov     word ptr [rsp+8B8h+var_870], ax
0x180015758  call    FormatRRASErrorString
0x18001575d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180015764  jz      short loc_1800157A0
0x180015766  lea     rax, [rbx+2B0h]
0x18001576d  mov     rcx, r13
0x180015770  test    rax, rax
0x180015773  lea     r9, [rsp+8B8h+var_880]
0x180015778  lea     r8, [rsp+8B8h+var_848]
0x18001577d  cmovnz  r9, rax
0x180015781  lea     rdx, RasRtrMgrParamTraceError
0x180015788  lea     rax, [rsp+8B8h+var_870]
0x18001578d  mov     [rsp+8B8h+var_890], rax
0x180015792  mov     rax, [rbx+48h]
0x180015796  mov     [rsp+8B8h+var_898], rax
0x18001579b  call    McTemplateU0zjzz_EventWriteTransfer
0x1800157a0  mov     eax, 8
0x1800157a5  jmp     loc_180015954
0x1800157aa  mov     eax, [rbx+29Ch]
0x1800157b0  xor     r9d, r9d
0x1800157b3  mov     [rdi], eax
0x1800157b5  test    esi, esi
0x1800157b7  jz      short loc_180015817
0x1800157b9  mov     eax, [rbx+2A0h]
0x1800157bf  mov     [rdi+4], eax
0x1800157c2  mov     eax, [rbx+214h]
0x1800157c8  mov     [rdi+8], eax
0x1800157cb  mov     rax, [rbx+218h]
0x1800157d2  mov     [rdi+10h], rax
0x1800157d6  cmp     [rbx+29Ch], r9d
0x1800157dd  jbe     loc_180015879
0x1800157e3  mov     rax, [rbx+2C8h]
0x1800157ea  mov     r8d, r9d
0x1800157ed  imul    rdx, r8, 1Ch
0x1800157f1  mov     ecx, [rdx+rax]
0x1800157f4  mov     [rdi+r9*8+18h], ecx
0x1800157f9  mov     rax, [rbx+2C8h]
0x180015800  mov     ecx, [rax+rdx+4]
0x180015804  mov     [rdi+r9*8+1Ch], ecx
0x180015809  inc     r9d
0x18001580c  cmp     r9d, [rbx+29Ch]
0x180015813  jb      short loc_1800157E3
0x180015815  jmp     short loc_180015879
0x180015817  movups  xmm0, xmmword ptr [rbx+2A0h]
0x18001581e  movdqu  xmmword ptr [rdi+4], xmm0
0x180015823  mov     eax, [rbx+214h]
0x180015829  mov     [rdi+14h], eax
0x18001582c  mov     rax, [rbx+218h]
0x180015833  mov     [rdi+18h], rax
0x180015837  cmp     [rbx+29Ch], r9d
0x18001583e  jbe     short loc_180015879
0x180015840  mov     eax, r9d
0x180015843  lea     r8, [r9+r9*4]
0x180015847  imul    rcx, rax, 1Ch
0x18001584b  mov     rax, [rbx+2C8h]
0x180015852  inc     r9d
0x180015855  movups  xmm0, xmmword ptr [rcx+rax+4]
0x18001585a  movdqu  xmmword ptr [rdi+r8*4+20h], xmm0
0x180015861  mov     rax, [rbx+2C8h]
0x180015868  mov     ecx, [rcx+rax]
0x18001586b  mov     [rdi+r8*4+30h], ecx
0x180015870  cmp     r9d, [rbx+29Ch]
0x180015877  jb      short loc_180015840
0x180015879  xor     r14d, r14d
0x18001587c  lea     rcx, stru_18008C4A0; Resource
0x180015883  mov     dl, 1; Wait
0x180015885  call    cs:__imp_RtlAcquireResourceShared
0x18001588b  lea     r15, [rbx+38h]
0x18001588f  mov     rsi, [r15]
0x180015892  mov     r8, rdi; lpMem
0x180015895  cmp     rsi, r15
0x180015898  jz      loc_180015935
0x18001589e  mov     rdx, [rsi+18h]
0x1800158a2  mov     rcx, rbx
0x1800158a5  call    BindInterfaceInProtocol
0x1800158aa  test    eax, eax
0x1800158ac  jz      short loc_18001592D
0x1800158ae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800158b5  jz      short loc_180015927
0x1800158b7  mov     r8, [rbx+48h]
0x1800158bb  lea     rdx, aBindinterfacei_0; "BindInterfaceInAllProtocols: Couldnt bi"...
0x1800158c2  xor     ecx, ecx
0x1800158c4  mov     dword ptr [rsp+8B8h+var_898], eax
0x1800158c8  mov     word ptr [rsp+8B8h+var_848], cx
0x1800158cd  mov     word ptr [rsp+8B8h+var_870], cx
0x1800158d2  lea     rcx, [rsp+8B8h+var_848]
0x1800158d7  mov     r9, [rsi+18h]
0x1800158db  mov     r9, [r9+20h]
0x1800158df  call    FormatRRASErrorString
0x1800158e4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800158eb  jz      short loc_180015927
0x1800158ed  lea     rax, [rbx+2B0h]
0x1800158f4  mov     rcx, r13
0x1800158f7  test    rax, rax
0x1800158fa  lea     r9, [rsp+8B8h+var_880]
0x1800158ff  lea     r8, [rsp+8B8h+var_848]
0x180015904  cmovnz  r9, rax
0x180015908  lea     rdx, RasRtrMgrParamTraceError
0x18001590f  lea     rax, [rsp+8B8h+var_870]
0x180015914  mov     [rsp+8B8h+var_890], rax
0x180015919  mov     rax, [rbx+48h]
0x18001591d  mov     [rsp+8B8h+var_898], rax
0x180015922  call    McTemplateU0zjzz_EventWriteTransfer
0x180015927  mov     r14d, 3EBh
0x18001592d  mov     rsi, [rsi]
0x180015930  jmp     loc_180015892
0x180015935  mov     rcx, cs:IPRouterHeap; hHeap
0x18001593c  xor     edx, edx; dwFlags
0x18001593e  call    cs:__imp_HeapFree
0x180015944  lea     rcx, stru_18008C4A0; Resource
0x18001594b  call    cs:__imp_RtlReleaseResource
0x180015951  mov     eax, r14d
0x180015954  mov     rcx, [rsp+8B8h+var_48]
0x18001595c  xor     rcx, rsp; StackCookie
0x18001595f  call    __security_check_cookie
0x180015964  add     rsp, 888h
0x18001596b  pop     r15
0x18001596d  pop     r14
0x18001596f  pop     r13
0x180015971  pop     rdi
0x180015972  pop     rsi
0x180015973  pop     rbx
0x180015974  retn
```
