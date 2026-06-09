# Siuf_EtwFromDM(_PCA_EVENT_TYPE,void *)

- ea: `0x180046d60`
- end: `0x180047398`
- name: `?Siuf_EtwFromDM@@YAKW4_PCA_EVENT_TYPE@@PEAX@Z`
- size: `1592`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001934`
- `0x180012920`
- `0x180019c84`
- `0x18001b320`
- `0x180025cc8`
- `0x18002a808`
- `0x180046d60`
- `0x180056256`
- `0x18007a9cf`
- `0x18007aa17`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180046f6d`
- `ntdll!RtlAllocateHeap` at `0x180046f6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047319`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046dcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046dcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004709f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004709f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180046ec8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180046ec8`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800472c4`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800472c4`

## string_xrefs

- `0x180046ec1`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Compatibility Assistant`
- `0x180047086`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Compatibility Assistant`
- `0x1800472ba`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Compatibility Assistant`
- `0x180046ed6`: `Failed to write payload [%d]`
- `0x1800472d5`: `Bad payload in registry [%d]`
- `0x180046f05`: `Failed to read question id [%d]`

## pseudocode

```c
__int64 __fastcall Siuf_EtwFromDM(__int64 a1, __int64 a2)
{
  RtlMemoryStream *v3; // rbx
  unsigned __int16 *v4; // rdi
  SIZE_T v5; // r14
  const char *v6; // r9
  int v7; // r8d
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  __int128 v10; // xmm6
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int16 *Heap; // rax
  int v14; // r8d
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  int v18; // esi
  LSTATUS ValueW; // eax
  int v20; // r8d
  int v21; // r9d
  unsigned __int64 v22; // rbx
  DWORD pcbData; // [rsp+C8h] [rbp-80h] BYREF
  int v25; // [rsp+CCh] [rbp-7Ch] BYREF
  int v26; // [rsp+D0h] [rbp-78h] BYREF
  int v27; // [rsp+D4h] [rbp-74h] BYREF
  int v28; // [rsp+D8h] [rbp-70h] BYREF
  int v29; // [rsp+DCh] [rbp-6Ch] BYREF
  int v30; // [rsp+E0h] [rbp-68h] BYREF
  int v31; // [rsp+E4h] [rbp-64h] BYREF
  unsigned __int16 *v32; // [rsp+E8h] [rbp-60h] BYREF
  unsigned __int16 *v33; // [rsp+F0h] [rbp-58h] BYREF
  unsigned __int16 *v34; // [rsp+F8h] [rbp-50h] BYREF
  unsigned __int16 *v35; // [rsp+100h] [rbp-48h] BYREF
  unsigned __int64 v36; // [rsp+108h] [rbp-40h] BYREF
  __int64 v37; // [rsp+110h] [rbp-38h] BYREF
  char *v38; // [rsp+118h] [rbp-30h] BYREF
  char *v39; // [rsp+120h] [rbp-28h] BYREF
  char *v40; // [rsp+128h] [rbp-20h] BYREF
  char *v41; // [rsp+130h] [rbp-18h] BYREF
  char *v42; // [rsp+138h] [rbp-10h] BYREF
  char *v43; // [rsp+140h] [rbp-8h] BYREF
  char *v44; // [rsp+148h] [rbp+0h] BYREF
  __int128 Buf1; // [rsp+150h] [rbp+8h] BYREF
  unsigned int Data; // [rsp+168h] [rbp+20h] BYREF
  __int128 Buf2; // [rsp+16Ch] [rbp+24h] BYREF
  __int64 v48; // [rsp+180h] [rbp+38h]
  __int64 v49; // [rsp+188h] [rbp+40h]
  char v50; // [rsp+190h] [rbp+48h] BYREF
  int v51; // [rsp+398h] [rbp+250h]
  char v52; // [rsp+39Ch] [rbp+254h] BYREF
  int v53; // [rsp+3ACh] [rbp+264h]
  int v54; // [rsp+3B0h] [rbp+268h]
  char v55; // [rsp+3B4h] [rbp+26Ch] BYREF
  char v56; // [rsp+40Eh] [rbp+2C6h] BYREF
  char v57; // [rsp+468h] [rbp+320h] BYREF
  char v58; // [rsp+670h] [rbp+528h] BYREF
  char v59; // [rsp+878h] [rbp+730h] BYREF
  int v60; // [rsp+A80h] [rbp+938h]
  __int64 v61; // [rsp+A88h] [rbp+940h]
  char v62; // [rsp+A90h] [rbp+948h] BYREF

  pcbData = 0;
  memset_0(&Data, 0, 0xB30u);
  v3 = *(RtlMemoryStream **)(a2 + 112);
  v4 = 0;
  v33 = 0;
  v32 = 0;
  v5 = *((_QWORD *)v3 + 1);
  *((_QWORD *)v3 + 4) = 0;
  EnterCriticalSection(&stru_180158698);
  if ( *(_OWORD *)(a2 + 56) != AE_LOG )
    goto LABEL_42;
  if ( *(_WORD *)(a2 + 72) == 70 )
  {
    dword_1801586D0 = 1;
    if ( qword_1801586D8 )
    {
      v8 = *((_QWORD *)v3 + 4);
      if ( v8 > *((_QWORD *)v3 + 1) || (v9 = v8 + 16, v8 + 16 < v8) || v9 > *((_QWORD *)v3 + 1) )
      {
        v6 = "Failed to read question id [%d]";
        v7 = 365;
      }
      else
      {
        v10 = *(_OWORD *)(*((_QWORD *)v3 + 5) + v8);
        *((_QWORD *)v3 + 4) = v9;
        memcpy_0(&Data, qword_1801586E0, 0xB30u);
        v48 = 0;
        v49 = MEMORY[0x7FFE0014];
        Buf2 = v10;
        PcaTracePrintf("Siuf", Data, 0, "Toast activated by CRE");
        if ( !RegSetKeyValueW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Compatibility Assistant",
                L"SiufState",
                3u,
                &Data,
                0xB30u) )
        {
          memset_0(qword_1801586E0, 0, 0xB30u);
          qword_1801586D8 = 0;
          goto LABEL_42;
        }
        v6 = "Failed to write payload [%d]";
        v7 = 390;
      }
    }
    else
    {
      v6 = "Received Siuf asked, but did not trigger [%d]";
      v7 = 355;
    }
    goto LABEL_41;
  }
  if ( *(_WORD *)(a2 + 72) != 81 )
    goto LABEL_42;
  v11 = *((_QWORD *)v3 + 4);
  if ( v11 > *((_QWORD *)v3 + 1) || (v12 = v11 + 16, v11 + 16 < v11) || v12 > *((_QWORD *)v3 + 1) )
  {
    v7 = 417;
    goto LABEL_40;
  }
  Buf1 = *(_OWORD *)(v11 + *((_QWORD *)v3 + 5));
  *((_QWORD *)v3 + 4) = v12;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v5);
  v4 = Heap;
  if ( !Heap )
  {
    v14 = 427;
LABEL_18:
    AslLogCallPrintf(1, (unsigned int)"Siuf_EtwFromDM", v14, (unsigned int)"Out of memory");
    goto LABEL_42;
  }
  v15 = v5 >> 1;
  if ( RtlMemoryStream::ReadString(v3, Heap, v15, &dword_1800FF0F4) )
  {
    v6 = "Bad SIUF event [%d]";
    v7 = 433;
LABEL_41:
    AslLogCallPrintf(1, (unsigned int)"Siuf_EtwFromDM", v7, (_DWORD)v6);
    goto LABEL_42;
  }
  if ( PcaUtilityDuplicateString(&v32, v4) )
  {
    v14 = 439;
    goto LABEL_18;
  }
  v16 = *((_QWORD *)v3 + 4);
  if ( v16 > *((_QWORD *)v3 + 1) || (v17 = v16 + 4, v16 + 4 < v16) || v17 > *((_QWORD *)v3 + 1) )
  {
    v7 = 449;
LABEL_40:
    v6 = "Bad SIUF event [%d]";
    goto LABEL_41;
  }
  v18 = *(_DWORD *)(v16 + *((_QWORD *)v3 + 5));
  *((_QWORD *)v3 + 4) = v17;
  if ( RtlMemoryStream::ReadString(v3, v4, v15, &dword_1800FF0F4) )
  {
    v6 = "Bad SIUF event [%d]";
    v7 = 459;
    goto LABEL_41;
  }
  if ( PcaUtilityDuplicateString(&v33, v4) )
  {
    v14 = 465;
    goto LABEL_18;
  }
  pcbData = 2864;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Compatibility Assistant",
             L"SiufState",
             8u,
             0,
             &Data,
             &pcbData);
  if ( ValueW )
  {
    if ( ValueW == 2 )
      goto LABEL_42;
    goto LABEL_37;
  }
  if ( pcbData != 2864 )
  {
LABEL_37:
    v6 = "Bad payload in registry [%d]";
    v7 = 483;
    goto LABEL_41;
  }
  if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    v22 = (MEMORY[0x7FFE0014] - v49) / 0x989680uLL;
    if ( (unsigned int)dword_180155AC8 > 5 )
    {
      v34 = v33;
      v35 = v32;
      v26 = dword_1801586D0;
      v37 = v61;
      v27 = v60;
      v38 = &v62;
      v39 = &v59;
      v40 = &v58;
      v41 = &v57;
      v42 = &v56;
      v43 = &v55;
      v44 = &v52;
      v28 = v51;
      *(_QWORD *)&Buf1 = &v50;
      v29 = v53;
      v30 = v54;
      v25 = v18;
      v36 = (MEMORY[0x7FFE0014] - v49) / 0x989680uLL;
      v31 = 2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        MEMORY[0x7FFE0014] - v49,
        (unsigned int)word_18013AC02,
        v20,
        v21,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&Buf1,
        (__int64)&v28,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v27,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v25,
        (__int64)&v34);
    }
    PcaTracePrintf("Siuf", Data, 0, "Feedback received,Value,%d,Time since asked,%d", v18, v22);
    memset_0(qword_1801586E0, 0, 0xB30u);
    qword_1801586D8 = 0;
    RegDeleteKeyValueW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Compatibility Assistant",
      L"SiufState");
  }
LABEL_42:
  LeaveCriticalSection(&stru_180158698);
  if ( v4 )
    AslFree(NtCurrentPeb()->ProcessHeap, v4);
  if ( v32 )
    AslFree(NtCurrentPeb()->ProcessHeap, v32);
  if ( v33 )
    AslFree(NtCurrentPeb()->ProcessHeap, v33);
  return 0;
}

```

## disassembly

```asm
0x180046d60  mov     rax, rsp
0x180046d63  push    rbp
0x180046d64  push    rbx
0x180046d65  push    rsi
0x180046d66  push    rdi
0x180046d67  push    r12
0x180046d69  push    r14
0x180046d6b  lea     rbp, [rax-0BA8h]
0x180046d72  sub     rsp, 0CB8h
0x180046d79  movaps  xmmword ptr [rax-48h], xmm6
0x180046d7d  mov     rax, cs:__security_cookie
0x180046d84  xor     rax, rsp
0x180046d87  mov     [rbp+0BA0h+var_50], rax
0x180046d8e  mov     rsi, rdx
0x180046d91  mov     [rbp+0BA0h+var_C20], 0
0x180046d98  mov     r12d, 0B30h
0x180046d9e  lea     rcx, [rbp+0BA0h+Data]; void *
0x180046da2  mov     r8d, r12d; Size
0x180046da5  xor     edx, edx; Val
0x180046da7  call    memset_0
0x180046dac  mov     rbx, [rsi+70h]
0x180046db0  lea     rcx, stru_180158698; lpCriticalSection
0x180046db7  xor     edi, edi
0x180046db9  mov     [rbp+0BA0h+var_BF8], rdi
0x180046dbd  mov     [rbp+0BA0h+var_C00], rdi
0x180046dc1  mov     r14, [rbx+8]
0x180046dc5  mov     qword ptr [rbx+20h], 0
0x180046dcd  call    cs:__imp_EnterCriticalSection
0x180046dd3  mov     rax, [rsi+38h]
0x180046dd7  cmp     rax, qword ptr cs:AE_LOG
0x180046dde  jnz     loc_180047312
0x180046de4  mov     rax, [rsi+40h]
0x180046de8  cmp     rax, qword ptr cs:AE_LOG+8
0x180046def  jnz     loc_180047312
0x180046df5  cmp     word ptr [rsi+48h], 46h ; 'F'
0x180046dfa  jnz     loc_180046F17
0x180046e00  cmp     cs:qword_1801586D8, rdi
0x180046e07  mov     cs:dword_1801586D0, 1
0x180046e11  jnz     short loc_180046E2D
0x180046e13  mov     dword ptr [rsp+0CE0h+lpData], 54Fh
0x180046e1b  lea     r9, aReceivedSiufAs; "Received Siuf asked, but did not trigge"...
0x180046e22  mov     r8d, 163h
0x180046e28  jmp     loc_180047301
0x180046e2d  mov     rcx, [rbx+20h]
0x180046e31  cmp     rcx, [rbx+8]
0x180046e35  ja      loc_180046F05
0x180046e3b  lea     rdx, [rcx+10h]
0x180046e3f  cmp     rdx, rcx
0x180046e42  jb      loc_180046F05
0x180046e48  cmp     rdx, [rbx+8]
0x180046e4c  ja      loc_180046F05
0x180046e52  mov     rax, [rbx+28h]
0x180046e56  movups  xmm6, xmmword ptr [rax+rcx]
0x180046e5a  mov     [rbx+20h], rdx
0x180046e5e  lea     rcx, [rbp+0BA0h+Data]; void *
0x180046e62  mov     r8, r12; Size
0x180046e65  lea     rdx, qword_1801586E0; Src
0x180046e6c  call    memcpy_0
0x180046e71  mov     ecx, 7FFE0014h
0x180046e76  mov     [rbp+0BA0h+var_B68], rdi
0x180046e7a  lea     r9, aToastActivated; "Toast activated by CRE"
0x180046e81  xor     r8d, r8d; unsigned int
0x180046e84  mov     rax, [rcx]
0x180046e87  lea     rcx, aSiuf; "Siuf"
0x180046e8e  mov     edx, [rbp+0BA0h+Data]; unsigned int
0x180046e91  mov     [rbp+0BA0h+var_B60], rax
0x180046e95  movdqu  [rbp+0BA0h+Buf2], xmm6
0x180046e9a  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180046e9f  lea     rax, [rbp+0BA0h+Data]
0x180046ea3  mov     [rsp+0CE0h+cbData], r12d; cbData
0x180046ea8  mov     r9d, 3; dwType
0x180046eae  mov     [rsp+0CE0h+lpData], rax; lpData
0x180046eb3  lea     r8, aSiufstate; "SiufState"
0x180046eba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046ec1  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180046ec8  call    cs:__imp_RegSetKeyValueW
0x180046ece  test    eax, eax
0x180046ed0  jz      short loc_180046EE8
0x180046ed2  mov     dword ptr [rsp+0CE0h+lpData], eax
0x180046ed6  lea     r9, aFailedToWriteP; "Failed to write payload [%d]"
0x180046edd  mov     r8d, 186h
0x180046ee3  jmp     loc_180047301
0x180046ee8  mov     r8, r12; Size
0x180046eeb  lea     rcx, qword_1801586E0; void *
0x180046ef2  xor     edx, edx; Val
0x180046ef4  call    memset_0
0x180046ef9  mov     cs:qword_1801586D8, rdi
0x180046f00  jmp     loc_180047312
0x180046f05  lea     r9, aFailedToReadQu; "Failed to read question id [%d]"
0x180046f0c  mov     r8d, 16Dh
0x180046f12  jmp     loc_1800472F9
0x180046f17  cmp     word ptr [rsi+48h], 51h ; 'Q'
0x180046f1c  jnz     loc_180047312
0x180046f22  mov     rcx, [rbx+20h]
0x180046f26  cmp     rcx, [rbx+8]
0x180046f2a  ja      loc_1800472EC
0x180046f30  lea     rdx, [rcx+10h]
0x180046f34  cmp     rdx, rcx
0x180046f37  jb      loc_1800472EC
0x180046f3d  cmp     rdx, [rbx+8]
0x180046f41  ja      loc_1800472EC
0x180046f47  mov     rax, [rbx+28h]
0x180046f4b  movups  xmm0, xmmword ptr [rcx+rax]
0x180046f4f  movdqu  [rbp+0BA0h+Buf1], xmm0
0x180046f54  mov     [rbx+20h], rdx
0x180046f58  mov     rcx, gs:60h
0x180046f61  mov     r8, r14; Size
0x180046f64  mov     edx, 8; Flags
0x180046f69  mov     rcx, [rcx+30h]; HeapHandle
0x180046f6d  call    cs:__imp_RtlAllocateHeap
0x180046f73  mov     rdi, rax
0x180046f76  test    rax, rax
0x180046f79  jnz     short loc_180046F9E
0x180046f7b  mov     r8d, 1ABh
0x180046f81  lea     r9, aOutOfMemory; "Out of memory"
0x180046f88  mov     ecx, 1
0x180046f8d  lea     rdx, aSiufEtwfromdm; "Siuf_EtwFromDM"
0x180046f94  call    AslLogCallPrintf
0x180046f99  jmp     loc_180047312
0x180046f9e  shr     r14, 1
0x180046fa1  lea     r9, dword_1800FF0F4; unsigned __int16 *
0x180046fa8  mov     r8, r14; unsigned __int64
0x180046fab  mov     rdx, rdi; unsigned __int16 *
0x180046fae  mov     rcx, rbx; this
0x180046fb1  call    ?ReadString@RtlMemoryStream@@QEAAKPEAG_KPEBG@Z; RtlMemoryStream::ReadString(ushort *,unsigned __int64,ushort const *)
0x180046fb6  test    eax, eax
0x180046fb8  jz      short loc_180046FD0
0x180046fba  mov     dword ptr [rsp+0CE0h+lpData], eax
0x180046fbe  lea     r9, aBadSiufEventD; "Bad SIUF event [%d]"
0x180046fc5  mov     r8d, 1B1h
0x180046fcb  jmp     loc_180047301
0x180046fd0  mov     rdx, rdi; unsigned __int16 *
0x180046fd3  lea     rcx, [rbp+0BA0h+var_C00]; unsigned __int16 **
0x180046fd7  call    ?PcaUtilityDuplicateString@@YAKPEAPEAGPEBG@Z; PcaUtilityDuplicateString(ushort * *,ushort const *)
0x180046fdc  test    eax, eax
0x180046fde  jz      short loc_180046FE8
0x180046fe0  mov     r8d, 1B7h
0x180046fe6  jmp     short loc_180046F81
0x180046fe8  mov     rcx, [rbx+20h]
0x180046fec  cmp     rcx, [rbx+8]
0x180046ff0  ja      loc_1800472E4
0x180046ff6  lea     rdx, [rcx+4]
0x180046ffa  cmp     rdx, rcx
0x180046ffd  jb      loc_1800472E4
0x180047003  cmp     rdx, [rbx+8]
0x180047007  ja      loc_1800472E4
0x18004700d  mov     rax, [rbx+28h]
0x180047011  mov     esi, [rcx+rax]
0x180047014  mov     [rbx+20h], rdx
0x180047018  lea     r9, dword_1800FF0F4; unsigned __int16 *
0x18004701f  mov     r8, r14; unsigned __int64
0x180047022  mov     rdx, rdi; unsigned __int16 *
0x180047025  mov     rcx, rbx; this
0x180047028  call    ?ReadString@RtlMemoryStream@@QEAAKPEAG_KPEBG@Z; RtlMemoryStream::ReadString(ushort *,unsigned __int64,ushort const *)
0x18004702d  test    eax, eax
0x18004702f  jz      short loc_180047047
0x180047031  mov     dword ptr [rsp+0CE0h+lpData], eax
0x180047035  lea     r9, aBadSiufEventD; "Bad SIUF event [%d]"
0x18004703c  mov     r8d, 1CBh
0x180047042  jmp     loc_180047301
0x180047047  mov     rdx, rdi; unsigned __int16 *
0x18004704a  lea     rcx, [rbp+0BA0h+var_BF8]; unsigned __int16 **
0x18004704e  call    ?PcaUtilityDuplicateString@@YAKPEAPEAGPEBG@Z; PcaUtilityDuplicateString(ushort * *,ushort const *)
0x180047053  test    eax, eax
0x180047055  jz      short loc_180047062
0x180047057  mov     r8d, 1D1h
0x18004705d  jmp     loc_180046F81
0x180047062  lea     rax, [rbp+0BA0h+var_C20]
0x180047066  mov     [rbp+0BA0h+var_C20], r12d
0x18004706a  mov     [rsp+0CE0h+pcbData], rax; pcbData
0x18004706f  lea     r8, aSiufstate; "SiufState"
0x180047076  lea     rax, [rbp+0BA0h+Data]
0x18004707a  mov     r14, 0FFFFFFFF80000002h
0x180047081  mov     qword ptr [rsp+0CE0h+cbData], rax; pvData
0x180047086  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004708d  mov     r9d, 8; dwFlags
0x180047093  mov     [rsp+0CE0h+lpData], 0; pdwType
0x18004709c  mov     rcx, r14; hkey
0x18004709f  call    cs:__imp_RegGetValueW
0x1800470a5  test    eax, eax
0x1800470a7  jnz     loc_1800472CC
0x1800470ad  cmp     [rbp+0BA0h+var_C20], r12d
0x1800470b1  jnz     loc_1800472D1
0x1800470b7  lea     r8d, [rax+10h]; Size
0x1800470bb  lea     rdx, [rbp+0BA0h+Buf2]; Buf2
0x1800470bf  lea     rcx, [rbp+0BA0h+Buf1]; Buf1
0x1800470c3  call    memcmp_0
0x1800470c8  test    eax, eax
0x1800470ca  jnz     loc_180047312
0x1800470d0  mov     ecx, 7FFE0014h
0x1800470d5  mov     rax, 0D6BF94D5E57A42BDh
0x1800470df  mov     rcx, [rcx]
0x1800470e2  sub     rcx, [rbp+0BA0h+var_B60]
0x1800470e6  mul     rcx
0x1800470e9  mov     eax, cs:dword_180155AC8
0x1800470ef  mov     rbx, rdx
0x1800470f2  shr     rbx, 17h
0x1800470f6  cmp     eax, 5
0x1800470f9  jbe     loc_180047276
0x1800470ff  mov     rax, [rbp+0BA0h+var_BF8]
0x180047103  lea     rdx, word_18013AC02
0x18004710a  mov     [rbp+0BA0h+var_BF0], rax
0x18004710e  mov     rax, [rbp+0BA0h+var_C00]
0x180047112  mov     [rbp+0BA0h+var_BE8], rax
0x180047116  mov     eax, cs:dword_1801586D0
0x18004711c  mov     [rbp+0BA0h+var_C18], eax
0x18004711f  mov     rax, [rbp+0BA0h+var_260]
0x180047126  mov     [rbp+0BA0h+var_BD8], rax
0x18004712a  mov     eax, [rbp+0BA0h+var_268]
0x180047130  mov     [rbp+0BA0h+var_C14], eax
0x180047133  lea     rax, [rbp+0BA0h+var_258]
0x18004713a  mov     [rbp+0BA0h+var_BD0], rax
0x18004713e  lea     rax, [rbp+0BA0h+var_470]
0x180047145  mov     [rbp+0BA0h+var_BC8], rax
0x180047149  lea     rax, [rbp+0BA0h+var_678]
0x180047150  mov     [rbp+0BA0h+var_BC0], rax
0x180047154  lea     rax, [rbp+0BA0h+var_880]
0x18004715b  mov     [rbp+0BA0h+var_BB8], rax
0x18004715f  lea     rax, [rbp+0BA0h+var_8DA]
0x180047166  mov     [rbp+0BA0h+var_BB0], rax
0x18004716a  lea     rax, [rbp+0BA0h+var_934]
0x180047171  mov     [rbp+0BA0h+var_BA8], rax
0x180047175  lea     rax, [rbp+0BA0h+var_94C]
0x18004717c  mov     [rbp+0BA0h+var_BA0], rax
0x180047180  mov     eax, [rbp+0BA0h+var_950]
0x180047186  mov     [rbp+0BA0h+var_C10], eax
0x180047189  lea     rax, [rbp+0BA0h+var_B58]
0x18004718d  mov     qword ptr [rbp+0BA0h+Buf1], rax
0x180047191  mov     eax, [rbp+0BA0h+var_93C]
0x180047197  mov     [rbp+0BA0h+var_C0C], eax
0x18004719a  mov     eax, [rbp+0BA0h+var_938]
0x1800471a0  mov     [rbp+0BA0h+var_C08], eax
0x1800471a3  lea     rax, [rbp+0BA0h+var_BF0]
0x1800471a7  mov     [rsp+0B0h], rax
0x1800471af  lea     rax, [rbp+0BA0h+var_C1C]
0x1800471b3  mov     [rsp+0CE0h+var_C38], rax
0x1800471bb  lea     rax, [rbp+0BA0h+var_BE8]
0x1800471bf  mov     [rsp+0CE0h+var_C40], rax
0x1800471c7  lea     rax, [rbp+0BA0h+var_C18]
0x1800471cb  mov     [rsp+0CE0h+var_C48], rax
0x1800471d3  lea     rax, [rbp+0BA0h+var_BE0]
0x1800471d7  mov     [rsp+0CE0h+var_C50], rax
0x1800471df  lea     rax, [rbp+0BA0h+var_BD8]
0x1800471e3  mov     [rsp+0CE0h+var_C58], rax
0x1800471eb  lea     rax, [rbp+0BA0h+var_C14]
0x1800471ef  mov     [rsp+0CE0h+var_C60], rax
0x1800471f7  lea     rax, [rbp+0BA0h+var_BD0]
0x1800471fb  mov     [rsp+0CE0h+var_C68], rax
0x180047200  lea     rax, [rbp+0BA0h+var_BC8]
0x180047204  mov     [rsp+0CE0h+var_C70], rax
0x180047209  lea     rax, [rbp+0BA0h+var_BC0]
0x18004720d  mov     [rsp+0CE0h+var_C78], rax
0x180047212  lea     rax, [rbp+0BA0h+var_BB8]
0x180047216  mov     [rsp+0CE0h+var_C80], rax
0x18004721b  lea     rax, [rbp+0BA0h+var_BB0]
0x18004721f  mov     [rsp+0CE0h+var_C88], rax
0x180047224  lea     rax, [rbp+0BA0h+var_BA8]
0x180047228  mov     [rsp+0CE0h+var_C90], rax
0x18004722d  lea     rax, [rbp+0BA0h+var_BA0]
0x180047231  mov     [rsp+0CE0h+var_C98], rax
0x180047236  lea     rax, [rbp+0BA0h+var_C10]
0x18004723a  mov     [rsp+0CE0h+var_CA0], rax
0x18004723f  lea     rax, [rbp+0BA0h+Buf1]
0x180047243  mov     [rsp+0CE0h+var_CA8], rax
0x180047248  lea     rax, [rbp+0BA0h+var_C0C]
0x18004724c  mov     [rsp+0CE0h+pcbData], rax
0x180047251  lea     rax, [rbp+0BA0h+var_C08]
0x180047255  mov     qword ptr [rsp+0CE0h+cbData], rax
0x18004725a  lea     rax, [rbp+0BA0h+var_C04]
0x18004725e  mov     [rsp+0CE0h+lpData], rax
0x180047263  mov     [rbp+0BA0h+var_C1C], esi
0x180047266  mov     [rbp+0BA0h+var_BE0], rbx
0x18004726a  mov     [rbp+0BA0h+var_C04], 2
0x180047271  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U2@U2@U2@U2@U1@U?$_tlgWrapperByVal@$07@@U4@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByRef@$0BA@@@4444443AEBU?$_tlgWrapperByVal@$07@@63434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180047276  mov     edx, [rbp+0BA0h+Data]; unsigned int
0x180047279  lea     r9, aFeedbackReceiv; "Feedback received,Value,%d,Time since a"...
0x180047280  mov     [rsp+0CE0h+cbData], ebx
0x180047284  lea     rcx, aSiuf; "Siuf"
0x18004728b  xor     r8d, r8d; unsigned int
0x18004728e  mov     dword ptr [rsp+0CE0h+lpData], esi
0x180047292  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180047297  mov     r8, r12; Size
0x18004729a  lea     rcx, qword_1801586E0; void *
0x1800472a1  xor     edx, edx; Val
0x1800472a3  call    memset_0
0x1800472a8  lea     r8, aSiufstate; "SiufState"
0x1800472af  mov     cs:qword_1801586D8, 0
0x1800472ba  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800472c1  mov     rcx, r14; hKey
0x1800472c4  call    cs:__imp_RegDeleteKeyValueW
0x1800472ca  jmp     short loc_180047312
0x1800472cc  cmp     eax, 2
0x1800472cf  jz      short loc_180047312
0x1800472d1  mov     dword ptr [rsp+0CE0h+lpData], eax
0x1800472d5  lea     r9, aBadPayloadInRe; "Bad payload in registry [%d]"
0x1800472dc  mov     r8d, 1E3h
0x1800472e2  jmp     short loc_180047301
0x1800472e4  mov     r8d, 1C1h
0x1800472ea  jmp     short loc_1800472F2
0x1800472ec  mov     r8d, 1A1h
  ... truncated ...
```
