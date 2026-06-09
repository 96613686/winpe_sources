# CSyncMLDPU::GetResultsData(uchar *,ulong)

- ea: `0x180005bd0`
- end: `0x180006099`
- name: `?GetResultsData@CSyncMLDPU@@UEAAJPEAEK@Z`
- size: `1225`
- prototype: `__int64 __fastcall(CSyncMLDPU *this, unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005bd0`
- `0x180014330`
- `0x180015174`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005ccb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000604e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005ccb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000604e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005dc6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005e78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005dc6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005e78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006072`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006072`
- `DMCmnUtils!CopyString` at `0x180005f75`
- `DMCmnUtils!CopyString` at `0x180005f75`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::GetResultsData(CSyncMLDPU *this, unsigned __int8 *a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  int v7; // ebx
  unsigned int v8; // edx
  unsigned __int64 v9; // rcx
  int v10; // r8d
  unsigned int v11; // eax
  unsigned int v12; // edx
  int v13; // eax
  __int64 v14; // r15
  HLOCAL v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  _WORD *v18; // rax
  int v19; // eax
  unsigned __int64 v20; // r15
  unsigned __int64 v21; // rax
  size_t v22; // rdi
  HLOCAL v23; // rax
  unsigned int v24; // edi
  __int64 v25; // r9
  unsigned int v27; // [rsp+38h] [rbp-49h] BYREF
  __int64 v28; // [rsp+40h] [rbp-41h]
  unsigned int v29; // [rsp+48h] [rbp-39h] BYREF
  __int64 v30; // [rsp+50h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-19h] BYREF
  __int16 *v33; // [rsp+78h] [rbp-9h]
  int v34; // [rsp+80h] [rbp-1h]
  int v35; // [rsp+84h] [rbp+3h]
  unsigned int *v36; // [rsp+88h] [rbp+7h]
  __int64 v37; // [rsp+90h] [rbp+Fh]

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  v28 = 0;
  v30 = 0;
  v29 = 0;
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v33 = &word_18003612E;
    UserData.Reserved = 2;
    v34 = 18;
    v35 = 1;
    v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  if ( a3 != 48 )
  {
    v7 = -2147024809;
    goto LABEL_37;
  }
  *(_DWORD *)a2 = *((_DWORD *)this + 59);
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 120LL))(*((_QWORD *)this + 32));
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 248LL))(*((_QWORD *)this + 32));
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(**((_QWORD **)this + 36) + 40LL))(
             *((_QWORD *)this + 36),
             v28,
             1,
             &v30);
      if ( v7 >= 0 )
      {
        if ( HIDWORD(v30) )
        {
          v7 = 122;
          goto LABEL_37;
        }
        v8 = v30;
        *((_QWORD *)a2 + 1) = 0;
        v9 = 31;
        v10 = *((_DWORD *)this + 11);
        if ( !v10 )
          v9 = 8;
        if ( (unsigned __int64)v8 >> 1 <= v9 )
        {
          v18 = LocalAlloc(0x40u, 2u);
          *((_QWORD *)a2 + 1) = v18;
          if ( !v18 )
          {
            v7 = -2147024882;
            goto LABEL_37;
          }
          *v18 = 0;
LABEL_28:
          *((_DWORD *)a2 + 6) = *((_DWORD *)this + 106);
          *((_QWORD *)a2 + 2) = *((_QWORD *)this + 54);
          v19 = *((_DWORD *)this + 61);
          *((_QWORD *)this + 54) = 0;
          *((_DWORD *)a2 + 1) = v19;
          *((_DWORD *)a2 + 7) = *((_DWORD *)this + 7);
          *((_DWORD *)a2 + 11) = *((_DWORD *)this + 111);
          v20 = (__int64)(*((_QWORD *)this + 39) - *((_QWORD *)this + 38)) >> 4;
          if ( !v20 )
            goto LABEL_37;
          v21 = 16LL * (unsigned int)v20;
          if ( v21 <= 0xFFFFFFFF )
          {
            v22 = (unsigned int)v21;
            v23 = LocalAlloc(0, (unsigned int)v21);
            *((_QWORD *)a2 + 4) = v23;
            if ( v23 )
            {
              memset_0(v23, 0, v22);
              v24 = 0;
              *((_DWORD *)a2 + 10) = v20;
              do
              {
                v25 = 16LL * v24;
                *(_DWORD *)(v25 + *((_QWORD *)a2 + 4) + 8) = *(_DWORD *)(v25 + *((_QWORD *)this + 38) + 8);
                v7 = CopyString(
                       *(const unsigned __int16 **)(*((_QWORD *)this + 38) + v25),
                       0xFFFFFFFF,
                       (unsigned __int16 **)(v25 + *((_QWORD *)a2 + 4)));
                if ( v7 < 0 )
                  break;
                ++v24;
              }
              while ( v24 < v20 );
            }
            else
            {
              v7 = -2147024882;
            }
            goto LABEL_37;
          }
LABEL_36:
          v7 = -2147024362;
          goto LABEL_37;
        }
        v11 = v8;
        v12 = (v8 >> 1) - 13;
        v13 = (v11 >> 1) - 36;
        if ( v10 )
          v12 = v13;
        if ( v12 + 1 < v12 )
          goto LABEL_36;
        v14 = 2 * (v12 + 1);
        v15 = LocalAlloc(0x40u, (unsigned int)v14);
        *((_QWORD *)a2 + 1) = v15;
        if ( !v15 )
        {
          v7 = -2147024882;
          goto LABEL_37;
        }
        v16 = 12;
        if ( *((_DWORD *)this + 11) )
          v16 = 58;
        v17 = *((_QWORD *)this + 36);
        LODWORD(v28) = v16;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL))(v17, v28, 0, 0);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 36) + 24LL))(
                 *((_QWORD *)this + 36),
                 *((_QWORD *)a2 + 1),
                 (unsigned int)(v14 - 2),
                 &v29);
          if ( v7 >= 0 )
          {
            if ( v14 - 2 != v29 )
            {
              v7 = 122;
              goto LABEL_37;
            }
            *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * ((unsigned __int64)v29 >> 1)) = 0;
            goto LABEL_28;
          }
        }
      }
    }
  }
LABEL_37:
  if ( (unsigned int)dword_18003E048 > 4 )
  {
    v27 = v7;
    v36 = &v27;
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v37 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v33 = (__int16 *)byte_180035ECD;
    UserData.Reserved = 2;
    v34 = 27;
    v35 = 1;
    LODWORD(v28) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( v3 )
    LeaveCriticalSection(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005bd0  mov     r11, rsp
0x180005bd3  push    rbp
0x180005bd4  push    rbx
0x180005bd5  push    r12
0x180005bd7  lea     rbp, [r11-5Fh]
0x180005bdb  sub     rsp, 0C0h
0x180005be2  mov     rax, cs:__security_cookie
0x180005be9  xor     rax, rsp
0x180005bec  mov     [rbp+57h+var_40], rax
0x180005bf0  mov     [r11+18h], rsi
0x180005bf4  lea     r12, [rcx+1D8h]
0x180005bfb  mov     [r11-28h], r13
0x180005bff  mov     rsi, rcx
0x180005c02  mov     [r11-30h], r14
0x180005c06  mov     rcx, r12; lpCriticalSection
0x180005c09  mov     [r11-38h], r15
0x180005c0d  mov     r14, rdx
0x180005c10  mov     ebx, r8d
0x180005c13  call    cs:__imp_EnterCriticalSection
0x180005c1a  nop     dword ptr [rax+rax+00h]
0x180005c1f  mov     eax, cs:dword_18003E048
0x180005c25  lea     r13, _TraceLoggingMetadataEnd
0x180005c2c  mov     [rbp+57h+var_98], 0
0x180005c34  lea     r15, _TraceLoggingMetadata
0x180005c3b  mov     [rbp+57h+var_88], 0
0x180005c43  mov     [rbp+57h+var_90], 0
0x180005c4a  cmp     eax, 5
0x180005c4d  jbe     loc_180005CD7
0x180005c53  movzx   eax, cs:word_180036124
0x180005c5a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180005c5e  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180005c61  xor     r9d, r9d; RelatedActivityId
0x180005c64  mov     rax, cs:off_18003E050
0x180005c6b  xor     r8d, r8d; ActivityId
0x180005c6e  mov     [rbp+57h+UserData.Ptr], rax
0x180005c72  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180005c79  mov     [rbp+57h+EventDescriptor.Keyword], 0
0x180005c81  movzx   eax, word ptr [rax]
0x180005c84  mov     [rbp+57h+UserData.Size], eax
0x180005c87  lea     rax, word_18003612E
0x180005c8e  mov     [rbp+57h+var_60], rax
0x180005c92  mov     rax, r13
0x180005c95  sub     eax, r15d
0x180005c98  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x180005c9f  mov     [rbp+57h+var_58], 12h
0x180005ca6  mov     [rbp+57h+var_54], 1
0x180005cad  mov     [rbp+57h+var_A0], eax
0x180005cb0  mov     eax, [rbp+57h+var_A0]
0x180005cb3  mov     rcx, cs:RegHandle; RegHandle
0x180005cba  lea     rax, [rbp+57h+UserData]
0x180005cbe  mov     [rsp+28h], rax; UserData
0x180005cc3  mov     [rsp+0D0h+UserDataCount], 2; UserDataCount
0x180005ccb  call    cs:__imp_EventWriteTransfer
0x180005cd2  nop     dword ptr [rax+rax+00h]
0x180005cd7  cmp     ebx, 30h ; '0'
0x180005cda  jz      short loc_180005CE6
0x180005cdc  mov     ebx, 80070057h
0x180005ce1  jmp     loc_180005FA6
0x180005ce6  mov     eax, [rsi+0ECh]
0x180005cec  mov     [r14], eax
0x180005cef  mov     rcx, [rsi+100h]
0x180005cf6  mov     rax, [rcx]
0x180005cf9  mov     rax, [rax+78h]
0x180005cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d02  mov     ebx, eax
0x180005d04  test    eax, eax
0x180005d06  js      loc_180005FA6
0x180005d0c  mov     rcx, [rsi+100h]
0x180005d13  mov     rax, [rcx]
0x180005d16  mov     rax, [rax+0F8h]
0x180005d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d22  mov     ebx, eax
0x180005d24  test    eax, eax
0x180005d26  js      loc_180005FA6
0x180005d2c  mov     rcx, [rsi+120h]
0x180005d33  lea     r9, [rbp+57h+var_88]
0x180005d37  mov     rdx, [rbp+57h+var_98]
0x180005d3b  mov     r8d, 1
0x180005d41  mov     rax, [rcx]
0x180005d44  mov     rax, [rax+28h]
0x180005d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4d  mov     ebx, eax
0x180005d4f  test    eax, eax
0x180005d51  js      loc_180005FA6
0x180005d57  cmp     dword ptr [rbp+57h+var_88+4], 0
0x180005d5b  jz      short loc_180005D67
0x180005d5d  mov     ebx, 7Ah ; 'z'
0x180005d62  jmp     loc_180005FA6
0x180005d67  mov     edx, dword ptr [rbp+57h+var_88]
0x180005d6a  mov     eax, 8
0x180005d6f  mov     qword ptr [r14+8], 0
0x180005d77  mov     ecx, 1Fh
0x180005d7c  mov     r8d, [rsi+2Ch]
0x180005d80  test    r8d, r8d
0x180005d83  mov     [rsp+0B8h], rdi
0x180005d8b  cmovz   ecx, eax
0x180005d8e  mov     eax, edx
0x180005d90  shr     rax, 1
0x180005d93  cmp     rax, rcx
0x180005d96  jbe     loc_180005E6E
0x180005d9c  mov     eax, edx
0x180005d9e  shr     edx, 1
0x180005da0  shr     eax, 1
0x180005da2  sub     edx, 0Dh
0x180005da5  sub     eax, 24h ; '$'
0x180005da8  test    r8d, r8d
0x180005dab  cmovnz  edx, eax
0x180005dae  lea     r15d, [rdx+1]
0x180005db2  cmp     r15d, edx
0x180005db5  jb      loc_180005F92
0x180005dbb  add     r15d, r15d
0x180005dbe  mov     ecx, 40h ; '@'; uFlags
0x180005dc3  mov     edx, r15d; uBytes
0x180005dc6  call    cs:__imp_LocalAlloc
0x180005dcd  nop     dword ptr [rax+rax+00h]
0x180005dd2  mov     [r14+8], rax
0x180005dd6  test    rax, rax
0x180005dd9  jnz     short loc_180005DE5
0x180005ddb  mov     ebx, 8007000Eh
0x180005de0  jmp     loc_180005F97
0x180005de5  cmp     dword ptr [rsi+2Ch], 0
0x180005de9  mov     eax, 0Ch
0x180005dee  mov     ecx, 3Ah ; ':'
0x180005df3  cmovnz  eax, ecx
0x180005df6  mov     rcx, [rsi+120h]
0x180005dfd  mov     dword ptr [rbp+57h+var_98], eax
0x180005e00  xor     r9d, r9d
0x180005e03  mov     rdx, [rbp+57h+var_98]
0x180005e07  xor     r8d, r8d
0x180005e0a  mov     rax, [rcx]
0x180005e0d  mov     rax, [rax+28h]
0x180005e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e16  mov     ebx, eax
0x180005e18  test    eax, eax
0x180005e1a  js      loc_180005F97
0x180005e20  mov     rcx, [rsi+120h]
0x180005e27  lea     r8d, [r15-2]
0x180005e2b  mov     rdx, [r14+8]
0x180005e2f  lea     r9, [rbp+57h+var_90]
0x180005e33  mov     rax, [rcx]
0x180005e36  mov     rax, [rax+18h]
0x180005e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e3f  mov     ebx, eax
0x180005e41  test    eax, eax
0x180005e43  js      loc_180005F97
0x180005e49  mov     edx, [rbp+57h+var_90]
0x180005e4c  lea     rax, [r15-2]
0x180005e50  cmp     rax, rdx
0x180005e53  jz      short loc_180005E5F
0x180005e55  mov     ebx, 7Ah ; 'z'
0x180005e5a  jmp     loc_180005F97
0x180005e5f  mov     rcx, [r14+8]
0x180005e63  shr     rdx, 1
0x180005e66  xor     eax, eax
0x180005e68  mov     [rcx+rdx*2], ax
0x180005e6c  jmp     short loc_180005E9F
0x180005e6e  mov     edx, 2; uBytes
0x180005e73  mov     ecx, 40h ; '@'; uFlags
0x180005e78  call    cs:__imp_LocalAlloc
0x180005e7f  nop     dword ptr [rax+rax+00h]
0x180005e84  mov     [r14+8], rax
0x180005e88  mov     rcx, rax
0x180005e8b  test    rax, rax
0x180005e8e  jnz     short loc_180005E9A
0x180005e90  mov     ebx, 8007000Eh
0x180005e95  jmp     loc_180005F9E
0x180005e9a  xor     eax, eax
0x180005e9c  mov     [rcx], ax
0x180005e9f  mov     eax, [rsi+1A8h]
0x180005ea5  mov     [r14+18h], eax
0x180005ea9  mov     rax, [rsi+1B0h]
0x180005eb0  mov     [r14+10h], rax
0x180005eb4  mov     eax, [rsi+0F4h]
0x180005eba  mov     qword ptr [rsi+1B0h], 0
0x180005ec5  mov     [r14+4], eax
0x180005ec9  mov     eax, [rsi+1Ch]
0x180005ecc  mov     [r14+1Ch], eax
0x180005ed0  mov     eax, [rsi+1BCh]
0x180005ed6  mov     [r14+2Ch], eax
0x180005eda  mov     r15, [rsi+138h]
0x180005ee1  sub     r15, [rsi+130h]
0x180005ee8  sar     r15, 4
0x180005eec  test    r15, r15
0x180005eef  jz      loc_180005F97
0x180005ef5  mov     eax, r15d
0x180005ef8  mov     ecx, 0FFFFFFFFh
0x180005efd  shl     rax, 4
0x180005f01  mov     ebx, r15d
0x180005f04  cmp     rax, rcx
0x180005f07  ja      loc_180005F92
0x180005f0d  mov     edx, eax; uBytes
0x180005f0f  xor     ecx, ecx; uFlags
0x180005f11  mov     edi, eax
0x180005f13  call    cs:__imp_LocalAlloc
0x180005f1a  nop     dword ptr [rax+rax+00h]
0x180005f1f  mov     [r14+20h], rax
0x180005f23  test    rax, rax
0x180005f26  jnz     short loc_180005F2F
0x180005f28  mov     ebx, 8007000Eh
0x180005f2d  jmp     short loc_180005F97
0x180005f2f  mov     r8, rdi; Size
0x180005f32  xor     edx, edx; Val
0x180005f34  mov     rcx, rax; void *
0x180005f37  call    memset_0
0x180005f3c  xor     edi, edi
0x180005f3e  mov     [r14+28h], ebx
0x180005f42  mov     rax, [rsi+130h]
0x180005f49  mov     rdx, [r14+20h]
0x180005f4d  mov     r9d, edi
0x180005f50  shl     r9, 4
0x180005f54  mov     eax, [r9+rax+8]
0x180005f59  mov     [r9+rdx+8], eax
0x180005f5e  mov     edx, 0FFFFFFFFh
0x180005f63  mov     rcx, [rsi+130h]
0x180005f6a  mov     r8, [r14+20h]
0x180005f6e  add     r8, r9
0x180005f71  mov     rcx, [rcx+r9]
0x180005f75  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180005f7c  nop     dword ptr [rax+rax+00h]
0x180005f81  mov     ebx, eax
0x180005f83  test    eax, eax
0x180005f85  js      short loc_180005F97
0x180005f87  inc     edi
0x180005f89  mov     eax, edi
0x180005f8b  cmp     rax, r15
0x180005f8e  jb      short loc_180005F42
0x180005f90  jmp     short loc_180005F97
0x180005f92  mov     ebx, 80070216h
0x180005f97  lea     r15, _TraceLoggingMetadata
0x180005f9e  mov     rdi, [rsp+0B8h]
0x180005fa6  mov     eax, cs:dword_18003E048
0x180005fac  mov     r14, [rsp+0D0h+var_28]
0x180005fb4  mov     rsi, [rsp+0D0h+arg_10]
0x180005fbc  cmp     eax, 4
0x180005fbf  jbe     loc_18000605A
0x180005fc5  lea     rax, [rbp+57h+var_A0]
0x180005fc9  mov     [rbp+57h+var_A0], ebx
0x180005fcc  mov     [rbp+57h+var_50], rax
0x180005fd0  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180005fd4  movzx   eax, cs:word_180035EC3
0x180005fdb  sub     r13d, r15d
0x180005fde  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180005fe1  xor     r9d, r9d; RelatedActivityId
0x180005fe4  mov     rax, cs:off_18003E050
0x180005feb  xor     r8d, r8d; ActivityId
0x180005fee  mov     [rbp+57h+UserData.Ptr], rax
0x180005ff2  mov     [rbp+57h+var_48], 4
0x180005ffa  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180006001  mov     [rbp+57h+EventDescriptor.Keyword], 0
0x180006009  movzx   eax, word ptr [rax]
0x18000600c  mov     [rbp+57h+UserData.Size], eax
0x18000600f  lea     rax, byte_180035ECD
0x180006016  mov     [rbp+57h+var_60], rax
0x18000601a  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x180006021  mov     [rbp+57h+var_58], 1Bh
0x180006028  mov     [rbp+57h+var_54], 1
0x18000602f  mov     dword ptr [rbp+57h+var_98], r13d
0x180006033  mov     eax, dword ptr [rbp+57h+var_98]
0x180006036  mov     rcx, cs:RegHandle; RegHandle
0x18000603d  lea     rax, [rbp+57h+UserData]
0x180006041  mov     [rsp+28h], rax; UserData
0x180006046  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x18000604e  call    cs:__imp_EventWriteTransfer
0x180006055  nop     dword ptr [rax+rax+00h]
0x18000605a  mov     r15, [rsp+0D0h+var_30]
0x180006062  mov     r13, [rsp+0D0h+var_20]
0x18000606a  test    r12, r12
0x18000606d  jz      short loc_18000607E
0x18000606f  mov     rcx, r12; lpCriticalSection
0x180006072  call    cs:__imp_LeaveCriticalSection
0x180006079  nop     dword ptr [rax+rax+00h]
0x18000607e  mov     eax, ebx
0x180006080  mov     rcx, [rbp+57h+var_40]
0x180006084  xor     rcx, rsp; StackCookie
0x180006087  call    __security_check_cookie
0x18000608c  add     rsp, 0C0h
0x180006093  pop     r12
0x180006095  pop     rbx
0x180006096  pop     rbp
0x180006097  retn
```
