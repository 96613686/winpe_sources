# LogAeEvent

- ea: `0x1800096e0`
- end: `0x180009a16`
- name: `LogAeEvent`
- size: `822`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lptstrFilename@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008250`
- `0x1800084d8`
- `0x180008bb8`
- `0x1800096e0`
- `0x18000e240`
- `0x1800191f0`

## import_xrefs

- `msvcrt!_itow_s` at `0x180009767`
- `msvcrt!_itow_s` at `0x1800097e3`
- `msvcrt!_itow_s` at `0x180009767`
- `msvcrt!_itow_s` at `0x1800097e3`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800099df`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800099df`

## string_xrefs

- `0x180009723`: `CompatibilityLayer: %ws`

## pseudocode

```c
__int64 __fastcall LogAeEvent(LPCWSTR lptstrFilename, WCHAR *a2, int a3, int a4, __int64 a5, __int64 a6)
{
  WCHAR *v8; // rdi
  unsigned int v10; // esi
  __int64 v11; // r8
  BOOL ExeInformation; // eax
  unsigned int v13; // r8d
  int ExeVersionAsString; // eax
  unsigned __int16 *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  int v28; // ecx
  unsigned __int8 v30[16]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 *v34; // [rsp+50h] [rbp-B0h]
  int v35; // [rsp+58h] [rbp-A8h]
  int v36; // [rsp+5Ch] [rbp-A4h]
  LPCWSTR v37; // [rsp+60h] [rbp-A0h]
  int v38; // [rsp+68h] [rbp-98h]
  int v39; // [rsp+6Ch] [rbp-94h]
  wchar_t *v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+78h] [rbp-88h]
  int v42; // [rsp+7Ch] [rbp-84h]
  WCHAR *v43; // [rsp+80h] [rbp-80h]
  int v44; // [rsp+88h] [rbp-78h]
  int v45; // [rsp+8Ch] [rbp-74h]
  wchar_t *v46; // [rsp+90h] [rbp-70h]
  int v47; // [rsp+98h] [rbp-68h]
  int v48; // [rsp+9Ch] [rbp-64h]
  WCHAR *v49; // [rsp+A0h] [rbp-60h]
  int v50; // [rsp+A8h] [rbp-58h]
  int v51; // [rsp+ACh] [rbp-54h]
  __int64 v52; // [rsp+B0h] [rbp-50h]
  int v53; // [rsp+B8h] [rbp-48h]
  int v54; // [rsp+BCh] [rbp-44h]
  __int64 v55; // [rsp+C0h] [rbp-40h]
  int v56; // [rsp+C8h] [rbp-38h]
  int v57; // [rsp+CCh] [rbp-34h]
  unsigned __int16 v58[24]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v59[32]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t Buffer[32]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR v61[256]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR v62[512]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR v63[1024]; // [rsp+780h] [rbp+680h] BYREF

  v30[0] = 0;
  v8 = a2;
  v10 = 0;
  AslLogCallPrintf(3, "LogAeEvent", 810, "CompatibilityLayer: %ws", a2);
  if ( !_itow_s(a4 != 0, Buffer, 0x20u, 10)
    && (unsigned int)LoadStringFromResourceFile(103 - (unsigned int)(a4 != 0), v63, 1024) )
  {
    if ( (ExeInformation = GetExeInformation(lptstrFilename, v61, v11, v30), v10 = ExeInformation, v30[0])
      && ExeInformation
      || (unsigned int)LoadStringFromResourceFile(0x68u, v61, 256) )
    {
      if ( !_itow_s(a3, v59, 0x20u, 10) )
      {
        if ( !v8 )
        {
          if ( !(unsigned int)LoadStringFromResourceFile(0x69u, v62, 512) )
            return v10;
          v8 = v62;
        }
        ExeVersionAsString = GetExeVersionAsString(lptstrFilename, v58, v13);
        v15 = v58;
        if ( !ExeVersionAsString )
          v15 = L"0.0.0.0";
        v16 = -1;
        v17 = -1;
        do
          ++v17;
        while ( v61[v17] );
        v33 = 0;
        v32 = 2 * v17 + 2;
        v18 = -1;
        v31 = v61;
        do
          ++v18;
        while ( v15[v18] );
        v34 = v15;
        v35 = 2 * v18 + 2;
        v36 = 0;
        if ( lptstrFilename )
        {
          v19 = -1;
          do
            ++v19;
          while ( lptstrFilename[v19] );
          v20 = 2 * v19 + 2;
        }
        else
        {
          v20 = 0;
        }
        v38 = v20;
        v21 = -1;
        v37 = lptstrFilename;
        v39 = 0;
        do
          ++v21;
        while ( v59[v21] );
        v42 = 0;
        v41 = 2 * v21 + 2;
        v40 = v59;
        v22 = -1;
        do
          ++v22;
        while ( v63[v22] );
        v45 = 0;
        v44 = 2 * v22 + 2;
        v43 = v63;
        v23 = -1;
        do
          ++v23;
        while ( Buffer[v23] );
        v48 = 0;
        v47 = 2 * v23 + 2;
        v46 = Buffer;
        if ( v8 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v8[v24] );
          v25 = 2 * v24 + 2;
        }
        else
        {
          v25 = 0;
        }
        v49 = v8;
        v50 = v25;
        v51 = 0;
        if ( a5 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)(a5 + 2 * v26) );
          v27 = 2 * v26 + 2;
        }
        else
        {
          v27 = 0;
        }
        v53 = v27;
        v52 = a5;
        v54 = 0;
        if ( a6 )
        {
          do
            ++v16;
          while ( *(_WORD *)(a6 + 2 * v16) );
          v28 = 2 * v16 + 2;
        }
        else
        {
          v28 = 0;
        }
        v56 = v28;
        v55 = a6;
        v57 = 0;
        EtwEventWriteNoRegistration(AE_LOG, AE_PCW_LOG_HELPED_USER_EVENT, 9, &v31);
        return 1;
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800096e0  mov     [rsp-8+arg_18], rbx
0x1800096e5  push    rbp
0x1800096e6  push    rsi
0x1800096e7  push    rdi
0x1800096e8  push    r12
0x1800096ea  push    r13
0x1800096ec  push    r14
0x1800096ee  push    r15
0x1800096f0  lea     rbp, [rsp-0E90h]
0x1800096f8  sub     rsp, 0F90h
0x1800096ff  mov     rax, cs:__security_cookie
0x180009706  xor     rax, rsp
0x180009709  mov     [rbp+0EC0h+var_40], rax
0x180009710  xor     r13d, r13d
0x180009713  mov     [rsp+0FC0h+var_FA0], rdx
0x180009718  mov     ebx, r9d
0x18000971b  mov     [rsp+0FC0h+var_F90], r13b
0x180009720  mov     r12d, r8d
0x180009723  lea     r9, aCompatibilityl; "CompatibilityLayer: %ws"
0x18000972a  mov     rdi, rdx
0x18000972d  mov     r14, rcx
0x180009730  lea     ecx, [r13+3]
0x180009734  mov     r8d, 32Ah
0x18000973a  lea     rdx, aLogaeevent_0; "LogAeEvent"
0x180009741  mov     esi, r13d
0x180009744  call    AslLogCallPrintf
0x180009749  mov     eax, ebx
0x18000974b  lea     r8d, [r13+20h]; BufferCount
0x18000974f  neg     eax
0x180009751  lea     rdx, [rbp+0EC0h+Buffer]; Buffer
0x180009755  mov     ecx, r13d
0x180009758  sbb     r15d, r15d
0x18000975b  test    ebx, ebx
0x18000975d  lea     ebx, [r13+0Ah]
0x180009761  mov     r9d, ebx; Radix
0x180009764  setnz   cl; Value
0x180009767  call    cs:__imp__itow_s
0x18000976d  test    eax, eax
0x18000976f  jnz     loc_1800099EA
0x180009775  mov     r8d, 400h; cchBufferMax
0x18000977b  lea     rdx, [rbp+0EC0h+var_840]; lpBuffer
0x180009782  lea     ecx, [r15+67h]; uID
0x180009786  call    ?LoadStringFromResourceFile@@YAHIPEAGH@Z; LoadStringFromResourceFile(uint,ushort *,int)
0x18000978b  test    eax, eax
0x18000978d  jz      loc_1800099EA
0x180009793  lea     r9, [rsp+0FC0h+var_F90]; unsigned __int8 *
0x180009798  mov     rcx, r14; pszPath
0x18000979b  lea     rdx, [rbp+0EC0h+var_E40]; unsigned __int16 *
0x1800097a2  call    ?GetExeInformation@@YAHPEBGPEAGKPEAE@Z; GetExeInformation(ushort const *,ushort *,ulong,uchar *)
0x1800097a7  mov     esi, eax
0x1800097a9  cmp     [rsp+0FC0h+var_F90], r13b
0x1800097ae  jz      short loc_1800097B4
0x1800097b0  test    eax, eax
0x1800097b2  jnz     short loc_1800097D3
0x1800097b4  mov     r8d, 100h; cchBufferMax
0x1800097ba  lea     rdx, [rbp+0EC0h+var_E40]; lpBuffer
0x1800097c1  mov     ecx, 68h ; 'h'; uID
0x1800097c6  call    ?LoadStringFromResourceFile@@YAHIPEAGH@Z; LoadStringFromResourceFile(uint,ushort *,int)
0x1800097cb  test    eax, eax
0x1800097cd  jz      loc_1800099EA
0x1800097d3  mov     r9d, ebx; Radix
0x1800097d6  lea     rdx, [rbp+0EC0h+var_EC0]; Buffer
0x1800097da  mov     r8d, 20h ; ' '; BufferCount
0x1800097e0  mov     ecx, r12d; Value
0x1800097e3  call    cs:__imp__itow_s
0x1800097e9  test    eax, eax
0x1800097eb  jnz     loc_1800099EA
0x1800097f1  test    rdi, rdi
0x1800097f4  jnz     short loc_18000981A
0x1800097f6  mov     r8d, 200h; cchBufferMax
0x1800097fc  lea     rdx, [rbp+0EC0h+var_C40]; lpBuffer
0x180009803  lea     ecx, [rax+69h]; uID
0x180009806  call    ?LoadStringFromResourceFile@@YAHIPEAGH@Z; LoadStringFromResourceFile(uint,ushort *,int)
0x18000980b  test    eax, eax
0x18000980d  jz      loc_1800099EA
0x180009813  lea     rdi, [rbp+0EC0h+var_C40]
0x18000981a  lea     rdx, [rbp+0EC0h+var_EF0]; unsigned __int16 *
0x18000981e  mov     rcx, r14; lptstrFilename
0x180009821  call    ?GetExeVersionAsString@@YAHPEBGPEAGK@Z; GetExeVersionAsString(ushort const *,ushort *,ulong)
0x180009826  test    eax, eax
0x180009828  lea     rcx, a0000; "0.0.0.0"
0x18000982f  lea     rdx, [rbp+0EC0h+var_EF0]
0x180009833  cmovz   rdx, rcx
0x180009837  lea     r8, [rbp+0EC0h+var_E40]
0x18000983e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009842  mov     rax, rcx
0x180009845  inc     rax
0x180009848  cmp     [r8+rax*2], r13w
0x18000984d  jnz     short loc_180009845
0x18000984f  lea     rax, ds:2[rax*2]
0x180009857  mov     [rsp+0FC0h+var_F74], r13d
0x18000985c  lea     r8, [rbp+0EC0h+var_E40]
0x180009863  mov     [rsp+0FC0h+var_F78], eax
0x180009867  mov     rax, rcx
0x18000986a  mov     [rsp+0FC0h+var_F80], r8
0x18000986f  inc     rax
0x180009872  cmp     [rdx+rax*2], r13w
0x180009877  jnz     short loc_18000986F
0x180009879  mov     [rsp+0FC0h+var_F70], rdx
0x18000987e  lea     rax, ds:2[rax*2]
0x180009886  mov     [rsp+0FC0h+var_F68], eax
0x18000988a  mov     [rsp+0FC0h+var_F64], r13d
0x18000988f  test    r14, r14
0x180009892  jz      short loc_1800098AB
0x180009894  mov     rax, rcx
0x180009897  inc     rax
0x18000989a  cmp     [r14+rax*2], r13w
0x18000989f  jnz     short loc_180009897
0x1800098a1  lea     rax, ds:2[rax*2]
0x1800098a9  jmp     short loc_1800098AE
0x1800098ab  mov     rax, r13
0x1800098ae  mov     [rsp+0FC0h+var_F58], eax
0x1800098b2  lea     rdx, [rbp+0EC0h+var_EC0]
0x1800098b6  mov     rax, rcx
0x1800098b9  mov     [rsp+0FC0h+var_F60], r14
0x1800098be  mov     [rsp+0FC0h+var_F54], r13d
0x1800098c3  inc     rax
0x1800098c6  cmp     [rdx+rax*2], r13w
0x1800098cb  jnz     short loc_1800098C3
0x1800098cd  lea     rax, ds:2[rax*2]
0x1800098d5  mov     [rsp+0FC0h+var_F44], r13d
0x1800098da  lea     rdx, [rbp+0EC0h+var_EC0]
0x1800098de  mov     [rsp+0FC0h+var_F48], eax
0x1800098e2  mov     [rsp+0FC0h+var_F50], rdx
0x1800098e7  mov     rax, rcx
0x1800098ea  lea     rdx, [rbp+0EC0h+var_840]
0x1800098f1  inc     rax
0x1800098f4  cmp     [rdx+rax*2], r13w
0x1800098f9  jnz     short loc_1800098F1
0x1800098fb  lea     rax, ds:2[rax*2]
0x180009903  mov     [rbp+0EC0h+var_F34], r13d
0x180009907  lea     rdx, [rbp+0EC0h+var_840]
0x18000990e  mov     [rbp+0EC0h+var_F38], eax
0x180009911  mov     [rbp+0EC0h+var_F40], rdx
0x180009915  mov     rax, rcx
0x180009918  lea     rdx, [rbp+0EC0h+Buffer]
0x18000991c  inc     rax
0x18000991f  cmp     [rdx+rax*2], r13w
0x180009924  jnz     short loc_18000991C
0x180009926  mov     [rbp+0EC0h+var_F24], r13d
0x18000992a  lea     rax, ds:2[rax*2]
0x180009932  mov     [rbp+0EC0h+var_F28], eax
0x180009935  lea     rdx, [rbp+0EC0h+Buffer]
0x180009939  mov     [rbp+0EC0h+var_F30], rdx
0x18000993d  test    rdi, rdi
0x180009940  jz      short loc_180009959
0x180009942  mov     rax, rcx
0x180009945  inc     rax
0x180009948  cmp     [rdi+rax*2], r13w
0x18000994d  jnz     short loc_180009945
0x18000994f  lea     rax, ds:2[rax*2]
0x180009957  jmp     short loc_18000995C
0x180009959  mov     rax, r13
0x18000995c  mov     rdx, [rbp+0EC0h+arg_20]
0x180009963  mov     [rbp+0EC0h+var_F20], rdi
0x180009967  mov     [rbp+0EC0h+var_F18], eax
0x18000996a  mov     [rbp+0EC0h+var_F14], r13d
0x18000996e  test    rdx, rdx
0x180009971  jz      short loc_18000998A
0x180009973  mov     rax, rcx
0x180009976  inc     rax
0x180009979  cmp     [rdx+rax*2], r13w
0x18000997e  jnz     short loc_180009976
0x180009980  lea     rax, ds:2[rax*2]
0x180009988  jmp     short loc_18000998D
0x18000998a  mov     rax, r13
0x18000998d  mov     [rbp+0EC0h+var_F08], eax
0x180009990  mov     rax, [rbp+0EC0h+arg_28]
0x180009997  mov     [rbp+0EC0h+var_F10], rdx
0x18000999b  mov     [rbp+0EC0h+var_F04], r13d
0x18000999f  test    rax, rax
0x1800099a2  jz      short loc_1800099B8
0x1800099a4  inc     rcx
0x1800099a7  cmp     [rax+rcx*2], r13w
0x1800099ac  jnz     short loc_1800099A4
0x1800099ae  lea     rcx, ds:2[rcx*2]
0x1800099b6  jmp     short loc_1800099BB
0x1800099b8  mov     rcx, r13
0x1800099bb  mov     [rbp+0EC0h+var_EF8], ecx
0x1800099be  lea     r9, [rsp+0FC0h+var_F80]
0x1800099c3  lea     rcx, AE_LOG
0x1800099ca  mov     [rbp+0EC0h+var_F00], rax
0x1800099ce  mov     r8d, 9
0x1800099d4  mov     [rbp+0EC0h+var_EF4], r13d
0x1800099d8  lea     rdx, AE_PCW_LOG_HELPED_USER_EVENT
0x1800099df  call    cs:__imp_EtwEventWriteNoRegistration
0x1800099e5  mov     esi, 1
0x1800099ea  mov     eax, esi
0x1800099ec  mov     rcx, [rbp+0EC0h+var_40]
0x1800099f3  xor     rcx, rsp; StackCookie
0x1800099f6  call    __security_check_cookie
0x1800099fb  mov     rbx, [rsp+0FC0h+arg_18]
0x180009a03  add     rsp, 0F90h
0x180009a0a  pop     r15
0x180009a0c  pop     r14
0x180009a0e  pop     r13
0x180009a10  pop     r12
0x180009a12  pop     rdi
0x180009a13  pop     rsi
0x180009a14  pop     rbp
0x180009a15  retn
```
