# CiLogSmartAppControlFailureDetails

- ea: `0x18006d254`
- end: `0x18006d782`
- name: `CiLogSmartAppControlFailureDetails`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800db63c`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x18006d254`

## import_xrefs

- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006d65b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006d6cf`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006d65b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006d6cf`
- `ntoskrnl!EtwEventEnabled` at `0x18006d2fc`
- `ntoskrnl!EtwEventEnabled` at `0x18006d2fc`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d725`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d725`
- `ntoskrnl!EtwWrite` at `0x18006d751`
- `ntoskrnl!EtwWrite` at `0x18006d751`

## pseudocode

```c
BOOLEAN __fastcall CiLogSmartAppControlFailureDetails(__int64 a1)
{
  BOOLEAN result; // al
  unsigned __int16 v3; // ax
  unsigned int v4; // ecx
  bool v5; // zf
  const GUID *ActivityIdThread; // rax
  __int16 v7; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v8; // [rsp+34h] [rbp-CCh] BYREF
  int v9; // [rsp+38h] [rbp-C8h] BYREF
  int v10; // [rsp+3Ch] [rbp-C4h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  int v14; // [rsp+4Ch] [rbp-B4h] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+54h] [rbp-ACh] BYREF
  BOOL v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+5Ch] [rbp-A4h] BYREF
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+64h] [rbp-9Ch] BYREF
  int v21; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING StringOut; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v23; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[36]; // [rsp+90h] [rbp-70h] BYREF

  v19 = 0;
  v16 = 0;
  v9 = 0;
  v7 = 0;
  v10 = 0;
  v12 = 0;
  v17 = 0;
  v15 = 0;
  v11 = 0;
  v18 = 0;
  v8 = 0;
  v13 = 0;
  v14 = 0;
  StringOut = 0;
  v23 = 0;
  memset(UserData, 0, sizeof(UserData));
  v20 = g_SmartAppControlEnforcementReason;
  v21 = g_SmartAppControlPreviousState;
  result = EtwEventEnabled(g_EtwEventHandle, &SmartAppControlBlockDetails);
  if ( result )
  {
    v3 = *(_WORD *)(a1 + 808);
    UserData[1].Size = v3;
    v7 = v3 >> 1;
    UserData[0].Ptr = (ULONGLONG)&v7;
    UserData[1].Ptr = *(_QWORD *)(a1 + 816);
    UserData[3].Ptr = a1 + 3348;
    UserData[3].Size = *(_DWORD *)(a1 + 3344);
    UserData[4].Ptr = a1 + 2120;
    UserData[6].Ptr = a1 + 2128;
    UserData[7].Ptr = a1 + 2116;
    UserData[8].Ptr = a1 + 2136;
    UserData[9].Ptr = a1 + 2108;
    UserData[10].Ptr = a1 + 2194;
    UserData[11].Ptr = a1 + 2186;
    UserData[12].Ptr = a1 + 2160;
    UserData[13].Ptr = a1 + 2164;
    UserData[14].Ptr = a1 + 2200;
    UserData[15].Ptr = a1 + 2224;
    UserData[16].Ptr = a1 + 2228;
    UserData[17].Ptr = a1 + 2168;
    UserData[18].Ptr = a1 + 2232;
    UserData[19].Ptr = a1 + 2092;
    UserData[2].Ptr = a1 + 3344;
    v4 = *(_DWORD *)(a1 + 2360);
    *(_QWORD *)&UserData[0].Size = 2;
    v9 = (v4 >> 10) & 1;
    UserData[20].Ptr = (ULONGLONG)&v9;
    UserData[1].Reserved = 0;
    v10 = HIWORD(v4) & 1;
    UserData[21].Ptr = (ULONGLONG)&v10;
    *(_QWORD *)&UserData[2].Size = 4;
    UserData[3].Reserved = 0;
    *(_QWORD *)&UserData[4].Size = 4;
    UserData[5].Ptr = a1 + 2124;
    *(_QWORD *)&UserData[5].Size = 4;
    *(_QWORD *)&UserData[6].Size = 4;
    *(_QWORD *)&UserData[7].Size = 4;
    *(_QWORD *)&UserData[8].Size = 4;
    *(_QWORD *)&UserData[9].Size = 8;
    *(_QWORD *)&UserData[10].Size = 4;
    *(_QWORD *)&UserData[11].Size = 8;
    *(_QWORD *)&UserData[12].Size = 4;
    *(_QWORD *)&UserData[13].Size = 4;
    *(_QWORD *)&UserData[14].Size = 4;
    *(_QWORD *)&UserData[15].Size = 4;
    *(_QWORD *)&UserData[16].Size = 4;
    *(_QWORD *)&UserData[17].Size = 16;
    *(_QWORD *)&UserData[18].Size = 16;
    *(_QWORD *)&UserData[19].Size = 1;
    *(_QWORD *)&UserData[20].Size = 4;
    v11 = *(unsigned __int8 *)(a1 + 2185);
    UserData[22].Ptr = (ULONGLONG)&v11;
    v12 = *(unsigned __int8 *)(a1 + 2184);
    UserData[23].Ptr = (ULONGLONG)&v12;
    *(_QWORD *)&UserData[21].Size = 4;
    v13 = (v4 >> 11) & 1;
    UserData[24].Ptr = (ULONGLONG)&v13;
    v14 = *(unsigned __int8 *)(a1 + 2248);
    UserData[25].Ptr = (ULONGLONG)&v14;
    v15 = (v4 >> 12) & 1;
    v5 = *(_DWORD *)(a1 + 2124) == 17;
    UserData[26].Ptr = (ULONGLONG)&v15;
    UserData[27].Ptr = (ULONGLONG)&v16;
    *(_QWORD *)&UserData[22].Size = 4;
    v17 = v5;
    UserData[28].Ptr = (ULONGLONG)&v17;
    v18 = *(_DWORD *)(a1 + 2072);
    UserData[29].Ptr = (ULONGLONG)&v18;
    UserData[30].Ptr = (ULONGLONG)&v20;
    UserData[31].Ptr = (ULONGLONG)&v21;
    *(_QWORD *)&UserData[23].Size = 4;
    *(_QWORD *)&UserData[24].Size = 4;
    *(_QWORD *)&UserData[25].Size = 4;
    *(_QWORD *)&UserData[26].Size = 4;
    v16 = (v4 >> 17) & 1;
    *(_QWORD *)&UserData[27].Size = 4;
    *(_QWORD *)&UserData[28].Size = 4;
    *(_QWORD *)&UserData[29].Size = 4;
    *(_QWORD *)&UserData[30].Size = 4;
    *(_QWORD *)&UserData[31].Size = 4;
    if ( *(_QWORD *)(a1 + 2152) )
    {
      RtlDuplicateUnicodeString(1u, (PCUNICODE_STRING)(a1 + 2144), &StringOut);
      v8 = StringOut.Length >> 1;
      UserData[32].Ptr = (ULONGLONG)&v8;
      UserData[33].Ptr = (ULONGLONG)StringOut.Buffer;
      UserData[33].Size = StringOut.Length;
      UserData[33].Reserved = 0;
    }
    else
    {
      UserData[32].Ptr = (ULONGLONG)&v19;
    }
    *(_QWORD *)&UserData[32].Size = 2;
    if ( *(_QWORD *)(a1 + 2216) )
    {
      RtlDuplicateUnicodeString(1u, (PCUNICODE_STRING)(a1 + 2208), &v23);
      *(_QWORD *)&UserData[34].Size = 16;
      UserData[34].Ptr = (ULONGLONG)&v23;
      UserData[35].Ptr = (ULONGLONG)v23.Buffer;
      UserData[35].Size = v23.Length;
      UserData[35].Reserved = 0;
    }
    else
    {
      *(_QWORD *)&UserData[34].Size = 2;
      UserData[34].Ptr = (ULONGLONG)&v19;
    }
    ActivityIdThread = (const GUID *)IoGetActivityIdThread();
    return EtwWrite(g_EtwEventHandle, &SmartAppControlBlockDetails, ActivityIdThread, 0x24u, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18006d254  mov     [rsp-8+arg_8], rbx
0x18006d259  mov     [rsp-8+arg_10], rdi
0x18006d25e  push    rbp
0x18006d25f  lea     rbp, [rsp-1E0h]
0x18006d267  sub     rsp, 2E0h
0x18006d26e  mov     rax, cs:__security_cookie
0x18006d275  xor     rax, rsp
0x18006d278  mov     [rbp+1E0h+var_10], rax
0x18006d27f  xor     edi, edi
0x18006d281  mov     rbx, rcx
0x18006d284  xorps   xmm0, xmm0
0x18006d287  mov     [rsp+2E0h+var_280], edi
0x18006d28b  xorps   xmm1, xmm1
0x18006d28e  mov     [rsp+2E0h+var_28C], edi
0x18006d292  lea     rcx, [rbp+1E0h+var_250]; void *
0x18006d296  mov     [rsp+2E0h+var_2A8], edi
0x18006d29a  xor     edx, edx; Val
0x18006d29c  mov     [rsp+2E0h+var_2B0], di
0x18006d2a1  mov     r8d, 240h; Size
0x18006d2a7  mov     [rsp+2E0h+var_2A4], edi
0x18006d2ab  mov     [rsp+2E0h+var_29C], edi
0x18006d2af  mov     [rsp+2E0h+var_288], edi
0x18006d2b3  mov     [rsp+2E0h+var_290], edi
0x18006d2b7  mov     [rsp+2E0h+var_2A0], edi
0x18006d2bb  mov     [rsp+2E0h+var_284], edi
0x18006d2bf  mov     [rsp+2E0h+var_2AC], di
0x18006d2c4  mov     [rsp+2E0h+var_298], edi
0x18006d2c8  mov     [rsp+2E0h+var_294], edi
0x18006d2cc  movups  xmmword ptr [rsp+2E0h+StringOut.Length], xmm0
0x18006d2d1  movups  xmmword ptr [rbp+1E0h+var_260.Length], xmm1
0x18006d2d5  call    memset
0x18006d2da  mov     eax, cs:g_SmartAppControlEnforcementReason
0x18006d2e0  lea     rdx, SmartAppControlBlockDetails; EventDescriptor
0x18006d2e7  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d2ee  mov     [rsp+2E0h+var_27C], eax
0x18006d2f2  mov     eax, cs:g_SmartAppControlPreviousState
0x18006d2f8  mov     [rsp+2E0h+var_278], eax
0x18006d2fc  call    cs:__imp_EtwEventEnabled
0x18006d303  nop     dword ptr [rax+rax+00h]
0x18006d308  test    al, al
0x18006d30a  jz      loc_18006D75D
0x18006d310  movzx   ecx, word ptr [rbx+328h]
0x18006d317  lea     rdx, [rbx+84Ch]
0x18006d31e  movzx   eax, cx
0x18006d321  mov     [rbp+1E0h+var_238], ecx
0x18006d324  shr     ax, 1
0x18006d327  lea     rcx, [rbx+0D10h]
0x18006d32e  mov     [rsp+2E0h+var_2B0], ax
0x18006d333  lea     rax, [rsp+2E0h+var_2B0]
0x18006d338  mov     [rbp+1E0h+var_250.Ptr], rax
0x18006d33c  mov     rax, [rbx+330h]
0x18006d343  mov     [rbp+1E0h+var_240], rax
0x18006d347  lea     rax, [rbx+0D14h]
0x18006d34e  mov     [rbp+1E0h+var_220], rax
0x18006d352  mov     eax, [rcx]
0x18006d354  mov     [rbp+1E0h+var_218], eax
0x18006d357  lea     rax, [rbx+848h]
0x18006d35e  mov     [rbp+1E0h+var_210], rax
0x18006d362  lea     rax, [rbx+850h]
0x18006d369  mov     [rbp+1E0h+var_1F0], rax
0x18006d36d  lea     rax, [rbx+844h]
0x18006d374  mov     [rbp+1E0h+var_1E0], rax
0x18006d378  lea     rax, [rbx+858h]
0x18006d37f  mov     [rbp+1E0h+var_1D0], rax
0x18006d383  lea     rax, [rbx+83Ch]
0x18006d38a  mov     [rbp+1E0h+var_1C0], rax
0x18006d38e  lea     rax, [rbx+892h]
0x18006d395  mov     [rbp+1E0h+var_1B0], rax
0x18006d399  lea     rax, [rbx+88Ah]
0x18006d3a0  mov     [rbp+1E0h+var_1A0], rax
0x18006d3a4  lea     rax, [rbx+870h]
0x18006d3ab  mov     [rbp+1E0h+var_190], rax
0x18006d3af  lea     rax, [rbx+874h]
0x18006d3b6  mov     [rbp+1E0h+var_180], rax
0x18006d3ba  lea     rax, [rbx+898h]
0x18006d3c1  mov     [rbp+1E0h+var_170], rax
0x18006d3c5  lea     rax, [rbx+8B0h]
0x18006d3cc  mov     [rbp+1E0h+var_160], rax
0x18006d3d3  lea     rax, [rbx+8B4h]
0x18006d3da  mov     [rbp+1E0h+var_150], rax
0x18006d3e1  lea     rax, [rbx+878h]
0x18006d3e8  mov     [rbp+1E0h+var_140], rax
0x18006d3ef  lea     rax, [rbx+8B8h]
0x18006d3f6  mov     [rbp+1E0h+var_130], rax
0x18006d3fd  lea     rax, [rbx+82Ch]
0x18006d404  mov     [rbp+1E0h+var_120], rax
0x18006d40b  mov     [rbp+1E0h+var_230], rcx
0x18006d40f  mov     ecx, [rbx+938h]
0x18006d415  mov     eax, ecx
0x18006d417  shr     eax, 0Ah
0x18006d41a  and     eax, 1
0x18006d41d  mov     qword ptr [rbp+1E0h+var_250.Size], 2
0x18006d425  mov     [rsp+2E0h+var_2A8], eax
0x18006d429  lea     rax, [rsp+2E0h+var_2A8]
0x18006d42e  mov     [rbp+1E0h+var_110], rax
0x18006d435  mov     eax, ecx
0x18006d437  shr     eax, 10h
0x18006d43a  and     eax, 1
0x18006d43d  mov     [rbp+1E0h+var_234], edi
0x18006d440  mov     [rsp+2E0h+var_2A4], eax
0x18006d444  lea     rax, [rsp+2E0h+var_2A4]
0x18006d449  mov     [rbp+1E0h+var_100], rax
0x18006d450  mov     [rbp+1E0h+var_228], 4
0x18006d458  mov     [rbp+1E0h+var_214], edi
0x18006d45b  mov     [rbp+1E0h+var_208], 4
0x18006d463  mov     [rbp+1E0h+var_200], rdx
0x18006d467  mov     [rbp+1E0h+var_1F8], 4
0x18006d46f  mov     [rbp+1E0h+var_1E8], 4
0x18006d477  mov     [rbp+1E0h+var_1D8], 4
0x18006d47f  mov     [rbp+1E0h+var_1C8], 4
0x18006d487  mov     [rbp+1E0h+var_1B8], 8
0x18006d48f  mov     [rbp+1E0h+var_1A8], 4
0x18006d497  mov     [rbp+1E0h+var_198], 8
0x18006d49f  mov     [rbp+1E0h+var_188], 4
0x18006d4a7  mov     [rbp+1E0h+var_178], 4
0x18006d4af  mov     [rbp+1E0h+var_168], 4
0x18006d4b7  mov     [rbp+1E0h+var_158], 4
0x18006d4c2  mov     [rbp+1E0h+var_148], 4
0x18006d4cd  mov     [rbp+1E0h+var_138], 10h
0x18006d4d8  mov     [rbp+1E0h+var_128], 10h
0x18006d4e3  mov     [rbp+1E0h+var_118], 1
0x18006d4ee  mov     [rbp+1E0h+var_108], 4
0x18006d4f9  movzx   eax, byte ptr [rbx+889h]
0x18006d500  mov     [rsp+2E0h+var_2A0], eax
0x18006d504  lea     rax, [rsp+2E0h+var_2A0]
0x18006d509  mov     [rbp+1E0h+var_F0], rax
0x18006d510  movzx   eax, byte ptr [rbx+888h]
0x18006d517  mov     [rsp+2E0h+var_29C], eax
0x18006d51b  lea     rax, [rsp+2E0h+var_29C]
0x18006d520  mov     [rbp+1E0h+var_E0], rax
0x18006d527  mov     eax, ecx
0x18006d529  shr     eax, 0Bh
0x18006d52c  and     eax, 1
0x18006d52f  mov     [rbp+1E0h+var_F8], 4
0x18006d53a  mov     [rsp+2E0h+var_298], eax
0x18006d53e  lea     rax, [rsp+2E0h+var_298]
0x18006d543  mov     [rbp+1E0h+var_D0], rax
0x18006d54a  movzx   eax, byte ptr [rbx+8C8h]
0x18006d551  mov     [rsp+2E0h+var_294], eax
0x18006d555  lea     rax, [rsp+2E0h+var_294]
0x18006d55a  mov     [rbp+1E0h+var_C0], rax
0x18006d561  mov     eax, ecx
0x18006d563  shr     eax, 0Ch
0x18006d566  and     eax, 1
0x18006d569  shr     ecx, 11h
0x18006d56c  mov     [rsp+2E0h+var_290], eax
0x18006d570  and     ecx, 1
0x18006d573  cmp     dword ptr [rdx], 11h
0x18006d576  lea     rax, [rsp+2E0h+var_290]
0x18006d57b  mov     [rbp+1E0h+var_B0], rax
0x18006d582  lea     rax, [rsp+2E0h+var_28C]
0x18006d587  mov     [rbp+1E0h+var_A0], rax
0x18006d58e  mov     eax, edi
0x18006d590  setz    al
0x18006d593  mov     [rbp+1E0h+var_E8], 4
0x18006d59e  mov     [rsp+2E0h+var_288], eax
0x18006d5a2  lea     rax, [rsp+2E0h+var_288]
0x18006d5a7  mov     [rbp+1E0h+var_90], rax
0x18006d5ae  mov     eax, [rbx+818h]
0x18006d5b4  mov     [rsp+2E0h+var_284], eax
0x18006d5b8  lea     rax, [rsp+2E0h+var_284]
0x18006d5bd  mov     [rbp+1E0h+var_80], rax
0x18006d5c4  lea     rax, [rsp+2E0h+var_27C]
0x18006d5c9  mov     [rbp+1E0h+var_70], rax
0x18006d5d0  lea     rax, [rsp+2E0h+var_278]
0x18006d5d5  mov     [rbp+1E0h+var_60], rax
0x18006d5dc  mov     [rbp+1E0h+var_D8], 4
0x18006d5e7  mov     [rbp+1E0h+var_C8], 4
0x18006d5f2  mov     [rbp+1E0h+var_B8], 4
0x18006d5fd  mov     [rbp+1E0h+var_A8], 4
0x18006d608  mov     [rsp+2E0h+var_28C], ecx
0x18006d60c  mov     [rbp+1E0h+var_98], 4
0x18006d617  mov     [rbp+1E0h+var_88], 4
0x18006d622  mov     [rbp+1E0h+var_78], 4
0x18006d62d  mov     [rbp+1E0h+var_68], 4
0x18006d638  mov     [rbp+1E0h+var_58], 4
0x18006d643  cmp     [rbx+868h], rdi
0x18006d64a  jz      short loc_18006D69F
0x18006d64c  lea     rdx, [rbx+860h]; StringIn
0x18006d653  lea     r8, [rsp+2E0h+StringOut]; StringOut
0x18006d658  lea     ecx, [rdi+1]; Flags
0x18006d65b  call    cs:__imp_RtlDuplicateUnicodeString
0x18006d662  nop     dword ptr [rax+rax+00h]
0x18006d667  movzx   eax, [rsp+2E0h+StringOut.Length]
0x18006d66c  shr     ax, 1
0x18006d66f  mov     [rsp+2E0h+var_2AC], ax
0x18006d674  lea     rax, [rsp+2E0h+var_2AC]
0x18006d679  mov     [rbp+1E0h+var_50], rax
0x18006d680  mov     rax, [rsp+2E0h+StringOut.Buffer]
0x18006d685  mov     [rbp+1E0h+var_40], rax
0x18006d68c  movzx   eax, [rsp+2E0h+StringOut.Length]
0x18006d691  mov     [rbp+1E0h+var_38], eax
0x18006d697  mov     [rbp+1E0h+var_34], edi
0x18006d69d  jmp     short loc_18006D6AB
0x18006d69f  lea     rax, [rsp+2E0h+var_280]
0x18006d6a4  mov     [rbp+1E0h+var_50], rax
0x18006d6ab  mov     [rbp+1E0h+var_48], 2
0x18006d6b6  cmp     [rbx+8A8h], rdi
0x18006d6bd  jz      short loc_18006D70E
0x18006d6bf  lea     rdx, [rbx+8A0h]; StringIn
0x18006d6c6  mov     ecx, 1; Flags
0x18006d6cb  lea     r8, [rbp+1E0h+var_260]; StringOut
0x18006d6cf  call    cs:__imp_RtlDuplicateUnicodeString
0x18006d6d6  nop     dword ptr [rax+rax+00h]
0x18006d6db  lea     rax, [rbp+1E0h+var_260]
0x18006d6df  mov     [rbp+1E0h+var_28], 10h
0x18006d6ea  mov     [rbp+1E0h+var_30], rax
0x18006d6f1  mov     rax, [rbp+1E0h+var_260.Buffer]
0x18006d6f5  mov     [rbp+1E0h+var_20], rax
0x18006d6fc  movzx   eax, [rbp+1E0h+var_260.Length]
0x18006d700  mov     [rbp+1E0h+var_18], eax
0x18006d706  mov     [rbp+1E0h+var_14], edi
0x18006d70c  jmp     short loc_18006D725
0x18006d70e  lea     rax, [rsp+2E0h+var_280]
0x18006d713  mov     [rbp+1E0h+var_28], 2
0x18006d71e  mov     [rbp+1E0h+var_30], rax
0x18006d725  call    cs:__imp_IoGetActivityIdThread
0x18006d72c  nop     dword ptr [rax+rax+00h]
0x18006d731  lea     rcx, [rbp+1E0h+var_250]
0x18006d735  mov     r9d, 24h ; '$'; UserDataCount
0x18006d73b  mov     [rsp+2E0h+UserData], rcx; UserData
0x18006d740  lea     rdx, SmartAppControlBlockDetails; EventDescriptor
0x18006d747  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d74e  mov     r8, rax; ActivityId
0x18006d751  call    cs:__imp_EtwWrite
0x18006d758  nop     dword ptr [rax+rax+00h]
0x18006d75d  mov     rcx, [rbp+1E0h+var_10]
0x18006d764  xor     rcx, rsp; StackCookie
0x18006d767  call    __security_check_cookie
0x18006d76c  lea     r11, [rsp+2E0h+var_s0]
0x18006d774  mov     rbx, [r11+18h]
0x18006d778  mov     rdi, [r11+20h]
0x18006d77c  mov     rsp, r11
0x18006d77f  pop     rbp
0x18006d780  retn
```
