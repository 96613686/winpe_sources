# CiLogSmartAppControlFailureDetails

- ea: `0x18006e028`
- end: `0x18006e556`
- name: `CiLogSmartAppControlFailureDetails`
- size: `1326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800dca2c`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18006e028`

## import_xrefs

- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006e42f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006e4a3`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006e42f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18006e4a3`
- `ntoskrnl!EtwEventEnabled` at `0x18006e0d0`
- `ntoskrnl!EtwEventEnabled` at `0x18006e0d0`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006e4f9`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006e4f9`
- `ntoskrnl!EtwWrite` at `0x18006e525`
- `ntoskrnl!EtwWrite` at `0x18006e525`

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
0x18006e028  mov     [rsp-8+arg_8], rbx
0x18006e02d  mov     [rsp-8+arg_10], rdi
0x18006e032  push    rbp
0x18006e033  lea     rbp, [rsp-1E0h]
0x18006e03b  sub     rsp, 2E0h
0x18006e042  mov     rax, cs:__security_cookie
0x18006e049  xor     rax, rsp
0x18006e04c  mov     [rbp+1E0h+var_10], rax
0x18006e053  xor     edi, edi
0x18006e055  mov     rbx, rcx
0x18006e058  xorps   xmm0, xmm0
0x18006e05b  mov     [rsp+2E0h+var_280], edi
0x18006e05f  xorps   xmm1, xmm1
0x18006e062  mov     [rsp+2E0h+var_28C], edi
0x18006e066  lea     rcx, [rbp+1E0h+var_250]; void *
0x18006e06a  mov     [rsp+2E0h+var_2A8], edi
0x18006e06e  xor     edx, edx; Val
0x18006e070  mov     [rsp+2E0h+var_2B0], di
0x18006e075  mov     r8d, 240h; Size
0x18006e07b  mov     [rsp+2E0h+var_2A4], edi
0x18006e07f  mov     [rsp+2E0h+var_29C], edi
0x18006e083  mov     [rsp+2E0h+var_288], edi
0x18006e087  mov     [rsp+2E0h+var_290], edi
0x18006e08b  mov     [rsp+2E0h+var_2A0], edi
0x18006e08f  mov     [rsp+2E0h+var_284], edi
0x18006e093  mov     [rsp+2E0h+var_2AC], di
0x18006e098  mov     [rsp+2E0h+var_298], edi
0x18006e09c  mov     [rsp+2E0h+var_294], edi
0x18006e0a0  movups  xmmword ptr [rsp+2E0h+StringOut.Length], xmm0
0x18006e0a5  movups  xmmword ptr [rbp+1E0h+var_260.Length], xmm1
0x18006e0a9  call    memset
0x18006e0ae  mov     eax, cs:g_SmartAppControlEnforcementReason
0x18006e0b4  lea     rdx, SmartAppControlBlockDetails; EventDescriptor
0x18006e0bb  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006e0c2  mov     [rsp+2E0h+var_27C], eax
0x18006e0c6  mov     eax, cs:g_SmartAppControlPreviousState
0x18006e0cc  mov     [rsp+2E0h+var_278], eax
0x18006e0d0  call    cs:__imp_EtwEventEnabled
0x18006e0d7  nop     dword ptr [rax+rax+00h]
0x18006e0dc  test    al, al
0x18006e0de  jz      loc_18006E531
0x18006e0e4  movzx   ecx, word ptr [rbx+328h]
0x18006e0eb  lea     rdx, [rbx+84Ch]
0x18006e0f2  movzx   eax, cx
0x18006e0f5  mov     [rbp+1E0h+var_238], ecx
0x18006e0f8  shr     ax, 1
0x18006e0fb  lea     rcx, [rbx+0D10h]
0x18006e102  mov     [rsp+2E0h+var_2B0], ax
0x18006e107  lea     rax, [rsp+2E0h+var_2B0]
0x18006e10c  mov     [rbp+1E0h+var_250.Ptr], rax
0x18006e110  mov     rax, [rbx+330h]
0x18006e117  mov     [rbp+1E0h+var_240], rax
0x18006e11b  lea     rax, [rbx+0D14h]
0x18006e122  mov     [rbp+1E0h+var_220], rax
0x18006e126  mov     eax, [rcx]
0x18006e128  mov     [rbp+1E0h+var_218], eax
0x18006e12b  lea     rax, [rbx+848h]
0x18006e132  mov     [rbp+1E0h+var_210], rax
0x18006e136  lea     rax, [rbx+850h]
0x18006e13d  mov     [rbp+1E0h+var_1F0], rax
0x18006e141  lea     rax, [rbx+844h]
0x18006e148  mov     [rbp+1E0h+var_1E0], rax
0x18006e14c  lea     rax, [rbx+858h]
0x18006e153  mov     [rbp+1E0h+var_1D0], rax
0x18006e157  lea     rax, [rbx+83Ch]
0x18006e15e  mov     [rbp+1E0h+var_1C0], rax
0x18006e162  lea     rax, [rbx+892h]
0x18006e169  mov     [rbp+1E0h+var_1B0], rax
0x18006e16d  lea     rax, [rbx+88Ah]
0x18006e174  mov     [rbp+1E0h+var_1A0], rax
0x18006e178  lea     rax, [rbx+870h]
0x18006e17f  mov     [rbp+1E0h+var_190], rax
0x18006e183  lea     rax, [rbx+874h]
0x18006e18a  mov     [rbp+1E0h+var_180], rax
0x18006e18e  lea     rax, [rbx+898h]
0x18006e195  mov     [rbp+1E0h+var_170], rax
0x18006e199  lea     rax, [rbx+8B0h]
0x18006e1a0  mov     [rbp+1E0h+var_160], rax
0x18006e1a7  lea     rax, [rbx+8B4h]
0x18006e1ae  mov     [rbp+1E0h+var_150], rax
0x18006e1b5  lea     rax, [rbx+878h]
0x18006e1bc  mov     [rbp+1E0h+var_140], rax
0x18006e1c3  lea     rax, [rbx+8B8h]
0x18006e1ca  mov     [rbp+1E0h+var_130], rax
0x18006e1d1  lea     rax, [rbx+82Ch]
0x18006e1d8  mov     [rbp+1E0h+var_120], rax
0x18006e1df  mov     [rbp+1E0h+var_230], rcx
0x18006e1e3  mov     ecx, [rbx+938h]
0x18006e1e9  mov     eax, ecx
0x18006e1eb  shr     eax, 0Ah
0x18006e1ee  and     eax, 1
0x18006e1f1  mov     qword ptr [rbp+1E0h+var_250.Size], 2
0x18006e1f9  mov     [rsp+2E0h+var_2A8], eax
0x18006e1fd  lea     rax, [rsp+2E0h+var_2A8]
0x18006e202  mov     [rbp+1E0h+var_110], rax
0x18006e209  mov     eax, ecx
0x18006e20b  shr     eax, 10h
0x18006e20e  and     eax, 1
0x18006e211  mov     [rbp+1E0h+var_234], edi
0x18006e214  mov     [rsp+2E0h+var_2A4], eax
0x18006e218  lea     rax, [rsp+2E0h+var_2A4]
0x18006e21d  mov     [rbp+1E0h+var_100], rax
0x18006e224  mov     [rbp+1E0h+var_228], 4
0x18006e22c  mov     [rbp+1E0h+var_214], edi
0x18006e22f  mov     [rbp+1E0h+var_208], 4
0x18006e237  mov     [rbp+1E0h+var_200], rdx
0x18006e23b  mov     [rbp+1E0h+var_1F8], 4
0x18006e243  mov     [rbp+1E0h+var_1E8], 4
0x18006e24b  mov     [rbp+1E0h+var_1D8], 4
0x18006e253  mov     [rbp+1E0h+var_1C8], 4
0x18006e25b  mov     [rbp+1E0h+var_1B8], 8
0x18006e263  mov     [rbp+1E0h+var_1A8], 4
0x18006e26b  mov     [rbp+1E0h+var_198], 8
0x18006e273  mov     [rbp+1E0h+var_188], 4
0x18006e27b  mov     [rbp+1E0h+var_178], 4
0x18006e283  mov     [rbp+1E0h+var_168], 4
0x18006e28b  mov     [rbp+1E0h+var_158], 4
0x18006e296  mov     [rbp+1E0h+var_148], 4
0x18006e2a1  mov     [rbp+1E0h+var_138], 10h
0x18006e2ac  mov     [rbp+1E0h+var_128], 10h
0x18006e2b7  mov     [rbp+1E0h+var_118], 1
0x18006e2c2  mov     [rbp+1E0h+var_108], 4
0x18006e2cd  movzx   eax, byte ptr [rbx+889h]
0x18006e2d4  mov     [rsp+2E0h+var_2A0], eax
0x18006e2d8  lea     rax, [rsp+2E0h+var_2A0]
0x18006e2dd  mov     [rbp+1E0h+var_F0], rax
0x18006e2e4  movzx   eax, byte ptr [rbx+888h]
0x18006e2eb  mov     [rsp+2E0h+var_29C], eax
0x18006e2ef  lea     rax, [rsp+2E0h+var_29C]
0x18006e2f4  mov     [rbp+1E0h+var_E0], rax
0x18006e2fb  mov     eax, ecx
0x18006e2fd  shr     eax, 0Bh
0x18006e300  and     eax, 1
0x18006e303  mov     [rbp+1E0h+var_F8], 4
0x18006e30e  mov     [rsp+2E0h+var_298], eax
0x18006e312  lea     rax, [rsp+2E0h+var_298]
0x18006e317  mov     [rbp+1E0h+var_D0], rax
0x18006e31e  movzx   eax, byte ptr [rbx+8C8h]
0x18006e325  mov     [rsp+2E0h+var_294], eax
0x18006e329  lea     rax, [rsp+2E0h+var_294]
0x18006e32e  mov     [rbp+1E0h+var_C0], rax
0x18006e335  mov     eax, ecx
0x18006e337  shr     eax, 0Ch
0x18006e33a  and     eax, 1
0x18006e33d  shr     ecx, 11h
0x18006e340  mov     [rsp+2E0h+var_290], eax
0x18006e344  and     ecx, 1
0x18006e347  cmp     dword ptr [rdx], 11h
0x18006e34a  lea     rax, [rsp+2E0h+var_290]
0x18006e34f  mov     [rbp+1E0h+var_B0], rax
0x18006e356  lea     rax, [rsp+2E0h+var_28C]
0x18006e35b  mov     [rbp+1E0h+var_A0], rax
0x18006e362  mov     eax, edi
0x18006e364  setz    al
0x18006e367  mov     [rbp+1E0h+var_E8], 4
0x18006e372  mov     [rsp+2E0h+var_288], eax
0x18006e376  lea     rax, [rsp+2E0h+var_288]
0x18006e37b  mov     [rbp+1E0h+var_90], rax
0x18006e382  mov     eax, [rbx+818h]
0x18006e388  mov     [rsp+2E0h+var_284], eax
0x18006e38c  lea     rax, [rsp+2E0h+var_284]
0x18006e391  mov     [rbp+1E0h+var_80], rax
0x18006e398  lea     rax, [rsp+2E0h+var_27C]
0x18006e39d  mov     [rbp+1E0h+var_70], rax
0x18006e3a4  lea     rax, [rsp+2E0h+var_278]
0x18006e3a9  mov     [rbp+1E0h+var_60], rax
0x18006e3b0  mov     [rbp+1E0h+var_D8], 4
0x18006e3bb  mov     [rbp+1E0h+var_C8], 4
0x18006e3c6  mov     [rbp+1E0h+var_B8], 4
0x18006e3d1  mov     [rbp+1E0h+var_A8], 4
0x18006e3dc  mov     [rsp+2E0h+var_28C], ecx
0x18006e3e0  mov     [rbp+1E0h+var_98], 4
0x18006e3eb  mov     [rbp+1E0h+var_88], 4
0x18006e3f6  mov     [rbp+1E0h+var_78], 4
0x18006e401  mov     [rbp+1E0h+var_68], 4
0x18006e40c  mov     [rbp+1E0h+var_58], 4
0x18006e417  cmp     [rbx+868h], rdi
0x18006e41e  jz      short loc_18006E473
0x18006e420  lea     rdx, [rbx+860h]; StringIn
0x18006e427  lea     r8, [rsp+2E0h+StringOut]; StringOut
0x18006e42c  lea     ecx, [rdi+1]; Flags
0x18006e42f  call    cs:__imp_RtlDuplicateUnicodeString
0x18006e436  nop     dword ptr [rax+rax+00h]
0x18006e43b  movzx   eax, [rsp+2E0h+StringOut.Length]
0x18006e440  shr     ax, 1
0x18006e443  mov     [rsp+2E0h+var_2AC], ax
0x18006e448  lea     rax, [rsp+2E0h+var_2AC]
0x18006e44d  mov     [rbp+1E0h+var_50], rax
0x18006e454  mov     rax, [rsp+2E0h+StringOut.Buffer]
0x18006e459  mov     [rbp+1E0h+var_40], rax
0x18006e460  movzx   eax, [rsp+2E0h+StringOut.Length]
0x18006e465  mov     [rbp+1E0h+var_38], eax
0x18006e46b  mov     [rbp+1E0h+var_34], edi
0x18006e471  jmp     short loc_18006E47F
0x18006e473  lea     rax, [rsp+2E0h+var_280]
0x18006e478  mov     [rbp+1E0h+var_50], rax
0x18006e47f  mov     [rbp+1E0h+var_48], 2
0x18006e48a  cmp     [rbx+8A8h], rdi
0x18006e491  jz      short loc_18006E4E2
0x18006e493  lea     rdx, [rbx+8A0h]; StringIn
0x18006e49a  mov     ecx, 1; Flags
0x18006e49f  lea     r8, [rbp+1E0h+var_260]; StringOut
0x18006e4a3  call    cs:__imp_RtlDuplicateUnicodeString
0x18006e4aa  nop     dword ptr [rax+rax+00h]
0x18006e4af  lea     rax, [rbp+1E0h+var_260]
0x18006e4b3  mov     [rbp+1E0h+var_28], 10h
0x18006e4be  mov     [rbp+1E0h+var_30], rax
0x18006e4c5  mov     rax, [rbp+1E0h+var_260.Buffer]
0x18006e4c9  mov     [rbp+1E0h+var_20], rax
0x18006e4d0  movzx   eax, [rbp+1E0h+var_260.Length]
0x18006e4d4  mov     [rbp+1E0h+var_18], eax
0x18006e4da  mov     [rbp+1E0h+var_14], edi
0x18006e4e0  jmp     short loc_18006E4F9
0x18006e4e2  lea     rax, [rsp+2E0h+var_280]
0x18006e4e7  mov     [rbp+1E0h+var_28], 2
0x18006e4f2  mov     [rbp+1E0h+var_30], rax
0x18006e4f9  call    cs:__imp_IoGetActivityIdThread
0x18006e500  nop     dword ptr [rax+rax+00h]
0x18006e505  lea     rcx, [rbp+1E0h+var_250]
0x18006e509  mov     r9d, 24h ; '$'; UserDataCount
0x18006e50f  mov     [rsp+2E0h+UserData], rcx; UserData
0x18006e514  lea     rdx, SmartAppControlBlockDetails; EventDescriptor
0x18006e51b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006e522  mov     r8, rax; ActivityId
0x18006e525  call    cs:__imp_EtwWrite
0x18006e52c  nop     dword ptr [rax+rax+00h]
0x18006e531  mov     rcx, [rbp+1E0h+var_10]
0x18006e538  xor     rcx, rsp; StackCookie
0x18006e53b  call    __security_check_cookie
0x18006e540  lea     r11, [rsp+2E0h+var_s0]
0x18006e548  mov     rbx, [r11+18h]
0x18006e54c  mov     rdi, [r11+20h]
0x18006e550  mov     rsp, r11
0x18006e553  pop     rbp
0x18006e554  retn
```
