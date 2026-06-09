# GetIpInfoForInterface

- ea: `0x1800180b4`
- end: `0x18001852a`
- name: `GetIpInfoForInterface`
- size: `1142`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001be68`

## callees

- `0x180001f90`
- `0x18000ac60`
- `0x180011790`
- `0x1800180b4`
- `0x180021700`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800184ff`
- `KERNEL32!HeapFree` at `0x1800184ff`
- `KERNEL32!HeapAlloc` at `0x1800183fe`
- `KERNEL32!HeapAlloc` at `0x1800183fe`

## string_xrefs

- `0x18001819c`: `GetIpInfoForInterface: NsiGetRoutingDomainIdForCompartment failed and returned %d`

## pseudocode

```c
__int64 __fastcall GetIpInfoForInterface(
        unsigned int a1,
        NET_IF_COMPARTMENT_ID a2,
        unsigned int *a3,
        _QWORD *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  int v9; // r15d
  __int64 v11; // r9
  unsigned int RoutingDomainIdForCompartment; // eax
  unsigned int v13; // ebx
  unsigned int IpAddrTable; // eax
  unsigned int *v16; // rbx
  unsigned int v17; // r14d
  char v18; // al
  __int64 v19; // rsi
  unsigned int v20; // edi
  unsigned int v21; // r9d
  LPVOID v22; // rax
  unsigned int v23; // ecx
  _DWORD *v24; // r11
  unsigned int v25; // r10d
  _DWORD *v26; // rdi
  unsigned int v27; // r9d
  unsigned int v28; // edx
  __int64 v29; // rdx
  __int64 v30; // [rsp+20h] [rbp-8C8h]
  __int64 v31; // [rsp+28h] [rbp-8C0h]
  LPVOID lpMem; // [rsp+30h] [rbp-8B8h] BYREF
  _DWORD *v33; // [rsp+38h] [rbp-8B0h]
  _DWORD *v34; // [rsp+40h] [rbp-8A8h]
  unsigned int *v35; // [rsp+48h] [rbp-8A0h]
  _OWORD v36[2]; // [rsp+50h] [rbp-898h] BYREF
  int v37; // [rsp+70h] [rbp-878h] BYREF
  __int128 v38; // [rsp+74h] [rbp-874h]
  __int128 v39; // [rsp+84h] [rbp-864h]
  int v40; // [rsp+94h] [rbp-854h]
  int v41; // [rsp+A0h] [rbp-848h] BYREF
  _BYTE v42[2044]; // [rsp+A4h] [rbp-844h] BYREF

  v35 = a3;
  v9 = 0;
  v34 = a5;
  v33 = a6;
  lpMem = 0;
  v41 = 0;
  v36[0] = GUID_NULL;
  memset_0(v42, 0, sizeof(v42));
  *a3 = 0;
  v37 = 0;
  v38 = 0;
  v40 = 0;
  *a5 = 1;
  *a6 = 0;
  *a4 = 0;
  v39 = 0;
  v36[1] = 0;
  if ( a2 != 1 )
  {
    if ( gIsRtrMgrEtwEnabled )
    {
      RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(a2, v36);
      v13 = RoutingDomainIdForCompartment;
      if ( RoutingDomainIdForCompartment )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v41) = 0;
          FormatRRASErrorString(
            &v41,
            L"GetIpInfoForInterface: NsiGetRoutingDomainIdForCompartment failed and returned %d",
            RoutingDomainIdForCompartment);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v41);
        }
        return v13;
      }
    }
  }
  IpAddrTable = AllocateAndGetIpAddrTable(&lpMem, a2, 1, v11, 0);
  v13 = IpAddrTable;
  if ( IpAddrTable )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v41) = 0;
      LOWORD(v37) = 0;
      FormatRRASErrorString(&v41, L"GetIpInfoForInterface: Error %d getting IP Address table from stack", IpAddrTable);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v41,
          (unsigned int)v36,
          0,
          (__int64)&v37);
    }
    return v13;
  }
  v16 = (unsigned int *)lpMem;
  v17 = 0;
  v18 = Microsoft_Windows_RRASEnableBits;
  v19 = 0;
  v20 = 8;
  while ( (unsigned int)v19 < *v16 )
  {
    if ( v16[6 * v19 + 2] == a1 && (v16[6 * v19 + 6] & 0x80000) == 0 )
    {
      v21 = v16[6 * v19 + 1];
      ++v9;
      if ( (unsigned int)(unsigned __int8)v21 - 1 <= 0xDE )
      {
        if ( v16[6 * v19 + 3] )
        {
          if ( (_DWORD)v19 == *v16 - 1 || v21 != v16[6 * (unsigned int)(v19 + 1) + 1] )
          {
            ++v17;
          }
          else if ( v18 < 0 )
          {
            LOWORD(v41) = 0;
            LOWORD(v37) = 0;
            LODWORD(v31) = HIBYTE(v16[6 * v19 + 1]);
            LODWORD(v30) = BYTE2(v16[6 * v19 + 1]);
            FormatRRASErrorString(
              &v41,
              L"GetIpInfoForInterface: %d.%d.%d.%d duplicate address",
              LOBYTE(v16[6 * v19 + 1]),
              BYTE1(v16[6 * v19 + 1]),
              v30,
              v31);
            v18 = Microsoft_Windows_RRASEnableBits;
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrmgrParamTraceInfo,
                (unsigned int)&v41,
                (unsigned int)v36,
                0,
                (__int64)&v37);
              v18 = Microsoft_Windows_RRASEnableBits;
            }
          }
        }
      }
    }
    v19 = (unsigned int)(v19 + 1);
  }
  if ( v17 )
  {
    v22 = HeapAlloc(IPRouterHeap, 8u, 28LL * v17);
    *a4 = v22;
    if ( v22 )
    {
      v23 = *v16;
      if ( *v16 )
      {
        v24 = v33;
        v25 = 0;
        v26 = v34;
        v27 = 0;
        do
        {
          if ( v16[6 * v27 + 2] == a1 )
          {
            v28 = v16[6 * v27 + 1];
            if ( (unsigned int)(unsigned __int8)v28 - 1 <= 0xDE
              && v16[6 * v27 + 3]
              && (v27 == v23 - 1 || v28 != v16[6 * v27 + 7]) )
            {
              if ( !*v24 )
              {
                *v24 = v16[6 * v27 + 5];
                *v26 = v16[6 * v27 + 4];
              }
              v29 = 28LL * v25++;
              *(_DWORD *)(v29 + *a4) = v16[6 * v27 + 1];
              *(_DWORD *)(v29 + *a4 + 4) = v16[6 * v27 + 3];
            }
          }
          v23 = *v16;
          ++v27;
        }
        while ( v27 < *v16 );
      }
      v20 = 0;
      *v35 = v17;
    }
    else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v37) = 0;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)L"GetIpInfoForInterface: Error allocating memory",
        (unsigned int)v36,
        0,
        (__int64)&v37);
    }
  }
  else
  {
    if ( v9 )
    {
      if ( v18 < 0 )
      {
        LOWORD(v41) = 0;
        LOWORD(v37) = 0;
        FormatRRASErrorString(&v41, L"GetIpInfoForInterface: If 0x%x has addresses entries which are 0s", a1);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v41,
            (unsigned int)v36,
            0,
            (__int64)&v37);
      }
    }
    v20 = 232;
  }
  HeapFree(IPRouterHeap, 0, v16);
  return v20;
}

```

## disassembly

```asm
0x1800180b4  push    rbx
0x1800180b6  push    rsi
0x1800180b7  push    rdi
0x1800180b8  push    r12
0x1800180ba  push    r13
0x1800180bc  push    r14
0x1800180be  push    r15
0x1800180c0  sub     rsp, 8B0h
0x1800180c7  mov     rax, cs:__security_cookie
0x1800180ce  xor     rax, rsp
0x1800180d1  mov     [rsp+8E8h+var_48], rax
0x1800180d9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800180e0  mov     r14, [rsp+8E8h+arg_20]
0x1800180e8  mov     rsi, r8
0x1800180eb  mov     rbx, [rsp+8E8h+arg_28]
0x1800180f3  mov     edi, edx
0x1800180f5  mov     [rsp+8E8h+var_8A0], r8
0x1800180fa  mov     r12d, ecx
0x1800180fd  xor     r15d, r15d
0x180018100  mov     [rsp+8E8h+var_8A8], r14
0x180018105  xor     edx, edx; Val
0x180018107  mov     [rsp+8E8h+var_8B0], rbx
0x18001810c  mov     r8d, 7FCh; Size
0x180018112  mov     [rsp+8E8h+lpMem], r15
0x180018117  lea     rcx, [rsp+8E8h+var_844]; void *
0x18001811f  mov     [rsp+8E8h+var_848], r15d
0x180018127  movdqu  [rsp+8E8h+var_898], xmm0
0x18001812d  mov     r13, r9
0x180018130  call    memset_0
0x180018135  mov     [rsi], r15d
0x180018138  xor     eax, eax
0x18001813a  xorps   xmm0, xmm0
0x18001813d  mov     [rsp+8E8h+var_878], r15d
0x180018142  movups  [rsp+8E8h+var_874], xmm0
0x180018147  mov     [rsp+8E8h+var_854], eax
0x18001814e  lea     esi, [rax+1]
0x180018151  mov     [r14], esi
0x180018154  mov     [rbx], r15d
0x180018157  mov     [r13+0], r15
0x18001815b  movups  [rsp+8E8h+var_864], xmm0
0x180018163  movups  [rsp+8E8h+var_888], xmm0
0x180018168  cmp     edi, esi
0x18001816a  jz      short loc_1800181DB
0x18001816c  cmp     cs:gIsRtrMgrEtwEnabled, r15d
0x180018173  jz      short loc_1800181DB
0x180018175  lea     rdx, [rsp+8E8h+var_898]
0x18001817a  mov     ecx, edi
0x18001817c  call    NsiGetRoutingDomainIdForCompartment
0x180018181  mov     ebx, eax
0x180018183  test    eax, eax
0x180018185  jz      short loc_1800181DB
0x180018187  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001818e  jge     short loc_1800181D4
0x180018190  mov     r8d, eax
0x180018193  mov     word ptr [rsp+8E8h+var_848], r15w
0x18001819c  lea     rdx, aGetipinfoforin_0; "GetIpInfoForInterface: NsiGetRoutingDom"...
0x1800181a3  lea     rcx, [rsp+8E8h+var_848]
0x1800181ab  call    FormatRRASErrorString
0x1800181b0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800181b7  jge     short loc_1800181D4
0x1800181b9  lea     r8, [rsp+8E8h+var_848]
0x1800181c1  lea     rdx, RasRtrmgrTraceInfo
0x1800181c8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800181cf  call    McTemplateU0z_EventWriteTransfer
0x1800181d4  mov     eax, ebx
0x1800181d6  jmp     loc_180018507
0x1800181db  mov     r8d, esi
0x1800181de  mov     dword ptr [rsp+8E8h+var_8C8], r15d
0x1800181e3  mov     edx, edi
0x1800181e5  lea     rcx, [rsp+8E8h+lpMem]
0x1800181ea  call    AllocateAndGetIpAddrTable
0x1800181ef  mov     ebx, eax
0x1800181f1  test    eax, eax
0x1800181f3  jz      short loc_180018261
0x1800181f5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800181fc  jz      short loc_1800181D4
0x1800181fe  mov     r8d, eax
0x180018201  mov     word ptr [rsp+8E8h+var_848], r15w
0x18001820a  lea     rdx, aGetipinfoforin_3; "GetIpInfoForInterface: Error %d getting"...
0x180018211  mov     word ptr [rsp+8E8h+var_878], r15w
0x180018217  lea     rcx, [rsp+8E8h+var_848]
0x18001821f  call    FormatRRASErrorString
0x180018224  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001822b  jz      short loc_1800181D4
0x18001822d  lea     rax, [rsp+8E8h+var_878]
0x180018232  mov     [rsp+8E8h+var_8C0], rax
0x180018237  lea     r9, [rsp+8E8h+var_898]
0x18001823c  lea     r8, [rsp+8E8h+var_848]
0x180018244  mov     [rsp+8E8h+var_8C8], r15
0x180018249  lea     rdx, RasRtrMgrParamTraceError
0x180018250  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180018257  call    McTemplateU0zjzz_EventWriteTransfer
0x18001825c  jmp     loc_1800181D4
0x180018261  mov     rbx, [rsp+8E8h+lpMem]
0x180018266  xor     r14d, r14d
0x180018269  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180018270  xor     esi, esi
0x180018272  lea     edi, [rsi+8]
0x180018275  mov     edx, [rbx]
0x180018277  cmp     esi, edx
0x180018279  jnb     loc_180018378
0x18001827f  lea     r8, [rsi+rsi*2]
0x180018283  cmp     [rbx+r8*8+8], r12d
0x180018288  jnz     loc_180018371
0x18001828e  test    [rbx+r8*8+1Ah], dil
0x180018293  jnz     loc_180018371
0x180018299  mov     r9d, [rbx+r8*8+4]
0x18001829e  inc     r15d
0x1800182a1  movzx   ecx, r9b
0x1800182a5  dec     ecx
0x1800182a7  cmp     ecx, 0DEh
0x1800182ad  ja      loc_180018371
0x1800182b3  cmp     dword ptr [rbx+r8*8+0Ch], 0
0x1800182b9  jz      loc_180018371
0x1800182bf  lea     ecx, [rdx-1]
0x1800182c2  cmp     esi, ecx
0x1800182c4  jz      loc_18001836E
0x1800182ca  lea     ecx, [rsi+1]
0x1800182cd  lea     rcx, [rcx+rcx*2]
0x1800182d1  cmp     r9d, [rbx+rcx*8+4]
0x1800182d6  jnz     loc_18001836E
0x1800182dc  test    al, al
0x1800182de  jns     loc_180018371
0x1800182e4  xor     eax, eax
0x1800182e6  lea     rdx, aGetipinfoforin_1; "GetIpInfoForInterface: %d.%d.%d.%d dupl"...
0x1800182ed  mov     word ptr [rsp+8E8h+var_848], ax
0x1800182f5  mov     word ptr [rsp+8E8h+var_878], ax
0x1800182fa  movzx   ecx, byte ptr [rbx+r8*8+6]
0x180018300  movzx   eax, byte ptr [rbx+r8*8+7]
0x180018306  movzx   r9d, byte ptr [rbx+r8*8+5]
0x18001830c  movzx   r8d, byte ptr [rbx+r8*8+4]
0x180018312  mov     dword ptr [rsp+8E8h+var_8C0], eax
0x180018316  mov     dword ptr [rsp+8E8h+var_8C8], ecx
0x18001831a  lea     rcx, [rsp+8E8h+var_848]
0x180018322  call    FormatRRASErrorString
0x180018327  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001832e  test    al, al
0x180018330  jns     short loc_180018371
0x180018332  lea     rax, [rsp+8E8h+var_878]
0x180018337  mov     [rsp+8E8h+var_8C0], rax
0x18001833c  lea     r9, [rsp+8E8h+var_898]
0x180018341  lea     r8, [rsp+8E8h+var_848]
0x180018349  mov     [rsp+8E8h+var_8C8], 0
0x180018352  lea     rdx, RasRtrmgrParamTraceInfo
0x180018359  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180018360  call    McTemplateU0zjzz_EventWriteTransfer
0x180018365  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001836c  jmp     short loc_180018371
0x18001836e  inc     r14d
0x180018371  inc     esi
0x180018373  jmp     loc_180018275
0x180018378  xor     esi, esi
0x18001837a  test    r14d, r14d
0x18001837d  jnz     short loc_1800183EE
0x18001837f  test    r15d, r15d
0x180018382  jz      short loc_1800183E4
0x180018384  test    al, al
0x180018386  jns     short loc_1800183E4
0x180018388  mov     r8d, r12d
0x18001838b  mov     word ptr [rsp+8E8h+var_848], si
0x180018393  lea     rdx, aGetipinfoforin; "GetIpInfoForInterface: If 0x%x has addr"...
0x18001839a  mov     word ptr [rsp+8E8h+var_878], si
0x18001839f  lea     rcx, [rsp+8E8h+var_848]
0x1800183a7  call    FormatRRASErrorString
0x1800183ac  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800183b3  jge     short loc_1800183E4
0x1800183b5  lea     rax, [rsp+8E8h+var_878]
0x1800183ba  mov     [rsp+8E8h+var_8C0], rax
0x1800183bf  lea     r9, [rsp+8E8h+var_898]
0x1800183c4  lea     r8, [rsp+8E8h+var_848]
0x1800183cc  mov     [rsp+8E8h+var_8C8], rsi
0x1800183d1  lea     rdx, RasRtrmgrParamTraceInfo
0x1800183d8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800183df  call    McTemplateU0zjzz_EventWriteTransfer
0x1800183e4  mov     edi, 0E8h
0x1800183e9  jmp     loc_1800184F3
0x1800183ee  mov     rcx, cs:IPRouterHeap; hHeap
0x1800183f5  mov     edx, edi; dwFlags
0x1800183f7  mov     eax, r14d
0x1800183fa  imul    r8, rax, 1Ch; dwBytes
0x1800183fe  call    cs:__imp_HeapAlloc
0x180018404  mov     [r13+0], rax
0x180018408  test    rax, rax
0x18001840b  jnz     short loc_180018452
0x18001840d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180018414  jz      loc_1800184F3
0x18001841a  lea     rax, [rsp+8E8h+var_878]
0x18001841f  mov     word ptr [rsp+8E8h+var_878], si
0x180018424  mov     [rsp+8E8h+var_8C0], rax
0x180018429  lea     r9, [rsp+8E8h+var_898]
0x18001842e  lea     r8, aGetipinfoforin_2; "GetIpInfoForInterface: Error allocating"...
0x180018435  mov     [rsp+8E8h+var_8C8], rsi
0x18001843a  lea     rdx, RasRtrMgrParamTraceError
0x180018441  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180018448  call    McTemplateU0zjzz_EventWriteTransfer
0x18001844d  jmp     loc_1800184F3
0x180018452  mov     ecx, [rbx]
0x180018454  test    ecx, ecx
0x180018456  jz      loc_1800184E9
0x18001845c  mov     r11, [rsp+8E8h+var_8B0]
0x180018461  mov     r10d, esi
0x180018464  mov     rdi, [rsp+8E8h+var_8A8]
0x180018469  mov     r9d, esi
0x18001846c  mov     eax, r9d
0x18001846f  lea     r8, [rax+rax*2]
0x180018473  cmp     [rbx+r8*8+8], r12d
0x180018478  jnz     short loc_1800184DF
0x18001847a  mov     edx, [rbx+r8*8+4]
0x18001847f  movzx   eax, dl
0x180018482  dec     eax
0x180018484  cmp     eax, 0DEh
0x180018489  ja      short loc_1800184DF
0x18001848b  cmp     [rbx+r8*8+0Ch], esi
0x180018490  jz      short loc_1800184DF
0x180018492  lea     eax, [rcx-1]
0x180018495  cmp     r9d, eax
0x180018498  jz      short loc_1800184A8
0x18001849a  lea     eax, [r9+1]
0x18001849e  lea     rax, [rax+rax*2]
0x1800184a2  cmp     edx, [rbx+rax*8+4]
0x1800184a6  jz      short loc_1800184DF
0x1800184a8  cmp     [r11], esi
0x1800184ab  jnz     short loc_1800184BC
0x1800184ad  mov     eax, [rbx+r8*8+14h]
0x1800184b2  mov     [r11], eax
0x1800184b5  mov     eax, [rbx+r8*8+10h]
0x1800184ba  mov     [rdi], eax
0x1800184bc  mov     rcx, [r13+0]
0x1800184c0  mov     eax, r10d
0x1800184c3  imul    rdx, rax, 1Ch
0x1800184c7  mov     eax, [rbx+r8*8+4]
0x1800184cc  inc     r10d
0x1800184cf  mov     [rdx+rcx], eax
0x1800184d2  mov     rcx, [r13+0]
0x1800184d6  mov     eax, [rbx+r8*8+0Ch]
0x1800184db  mov     [rdx+rcx+4], eax
0x1800184df  mov     ecx, [rbx]
0x1800184e1  inc     r9d
0x1800184e4  cmp     r9d, ecx
0x1800184e7  jb      short loc_18001846C
0x1800184e9  mov     rax, [rsp+8E8h+var_8A0]
0x1800184ee  mov     edi, esi
0x1800184f0  mov     [rax], r14d
0x1800184f3  mov     rcx, cs:IPRouterHeap; hHeap
0x1800184fa  mov     r8, rbx; lpMem
0x1800184fd  xor     edx, edx; dwFlags
0x1800184ff  call    cs:__imp_HeapFree
0x180018505  mov     eax, edi
0x180018507  mov     rcx, [rsp+8E8h+var_48]
0x18001850f  xor     rcx, rsp; StackCookie
0x180018512  call    __security_check_cookie
0x180018517  add     rsp, 8B0h
0x18001851e  pop     r15
0x180018520  pop     r14
0x180018522  pop     r13
0x180018524  pop     r12
0x180018526  pop     rdi
0x180018527  pop     rsi
0x180018528  pop     rbx
0x180018529  retn
```
