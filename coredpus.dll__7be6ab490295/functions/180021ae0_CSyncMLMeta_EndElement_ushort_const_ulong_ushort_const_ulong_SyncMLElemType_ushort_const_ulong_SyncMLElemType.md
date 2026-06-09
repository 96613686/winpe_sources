# CSyncMLMeta::EndElement(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort const *,ulong,SyncMLElemType *)

- ea: `0x180021ae0`
- end: `0x180022209`
- name: `?EndElement@CSyncMLMeta@@QEAAJPEBGK0KW4SyncMLElemType@@0KPEAW42@@Z`
- size: `1833`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008d30`
- `0x18000d510`
- `0x1800203e0`

## callees

- `0x1800043f0`
- `0x180010f60`
- `0x1800110e4`
- `0x180014330`
- `0x180021ae0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180021f22`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180021f22`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021cdd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021daa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021ff2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800220ee`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800221e1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021cdd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021daa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021ff2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800220ee`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800221e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021cfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022021`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002212d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002213e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021cfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022021`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002212d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002213e`
- `DMCmnUtils!InvStrCmpNIW` at `0x180021bef`
- `DMCmnUtils!InvStrCmpNIW` at `0x180021ecc`
- `DMCmnUtils!InvStrCmpNIW` at `0x180021bef`
- `DMCmnUtils!InvStrCmpNIW` at `0x180021ecc`
- `DMCmnUtils!CopyString` at `0x180021e0e`
- `DMCmnUtils!CopyString` at `0x180021e0e`

## pseudocode

```c
__int64 __fastcall CSyncMLMeta::EndElement(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        const unsigned __int16 *a7,
        unsigned int a8,
        __int64 a9)
{
  int v9; // ebx
  const unsigned __int16 *v10; // rsi
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned __int16 *v13; // rax
  __int64 v14; // rdi
  unsigned __int16 *v15; // rcx
  unsigned int v16; // r14d
  unsigned __int16 *v17; // rcx
  HLOCAL v18; // rcx
  __int64 v19; // rcx
  const unsigned __int16 *v20; // rax
  unsigned __int64 v21; // r15
  __int64 v22; // rbx
  unsigned int v23; // eax
  unsigned __int16 *v24; // rcx
  wchar_t *EndPtr; // [rsp+48h] [rbp-91h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-89h] BYREF
  unsigned __int16 *v28; // [rsp+58h] [rbp-81h] BYREF
  EVENT_DESCRIPTOR v29; // [rsp+60h] [rbp-79h] BYREF
  HLOCAL v30; // [rsp+70h] [rbp-69h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-51h] BYREF
  char *v33; // [rsp+98h] [rbp-41h]
  int v34; // [rsp+A0h] [rbp-39h]
  int v35; // [rsp+A4h] [rbp-35h]
  wchar_t **p_EndPtr; // [rsp+A8h] [rbp-31h]
  __int64 v37; // [rsp+B0h] [rbp-29h]

  *(_QWORD *)&v29.Id = a9;
  *(_QWORD *)&EventDescriptor.Id = a1;
  v28 = 0;
  hMem = 0;
  LODWORD(EndPtr) = 0;
  v9 = CanonicalizeTag(a4, a5, a2, a3, a6, &v28, (unsigned int *)&EndPtr);
  if ( v9 < 0 )
    goto LABEL_61;
  v10 = v28;
  if ( !v28 || !*v28 )
  {
    v9 = -2147024809;
    v15 = v28;
    goto LABEL_36;
  }
  v11 = (unsigned int)EndPtr;
  if ( (unsigned int)EndPtr == 0xFFFFFFFFLL )
  {
    v12 = 0x7FFFFFFF;
    v13 = v28;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
    v11 = 0x7FFFFFFF - v12;
    if ( !v12 )
    {
LABEL_14:
      v9 = -2102788095;
      v15 = (unsigned __int16 *)v10;
LABEL_36:
      LocalFree(v15);
      LocalFree(hMem);
      goto LABEL_62;
    }
  }
  v14 = 0;
  while ( InvStrCmpNIW(v10, (&c_rgszSyncMLElem)[v14], v11) || (&c_rgszSyncMLElem)[v14][v11] )
  {
    v14 = (unsigned int)(v14 + 1);
    if ( (int)v14 >= 73 )
    {
      v10 = v28;
      goto LABEL_14;
    }
  }
  if ( (_DWORD)v14 == 23 )
  {
    v9 = 0;
LABEL_55:
    v24 = v28;
    **(_DWORD **)&v29.Id = v14;
    LocalFree(v24);
    LocalFree(hMem);
    goto LABEL_56;
  }
  v16 = CSyncMLMeta::SyncMLElemToPropIndex((unsigned int)v14);
  if ( v16 != -1 )
  {
    if ( !a7 || !*a7 )
    {
      if ( (unsigned int)dword_18003E048 > 2 )
      {
        *(_DWORD *)&v29.Level = 2;
        UserData.Ptr = (ULONGLONG)off_18003E050;
        *(_DWORD *)&v29.Id = 184549376;
        v29.Keyword = 0;
        UserData.Size = (unsigned __int16)*off_18003E050;
        v33 = byte_180037443;
        UserData.Reserved = 2;
        v34 = 17;
        v35 = 1;
        LODWORD(EndPtr) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &v29, 0, 0, 2u, &UserData);
      }
      goto LABEL_23;
    }
    v9 = CopyString(a7, a8, (unsigned __int16 **)&hMem);
    if ( v9 >= 0 )
    {
      v18 = hMem;
      v30 = hMem;
      if ( v16 > 4 )
      {
        if ( (_DWORD)v14 == 44 )
        {
          if ( !*a7 )
          {
LABEL_35:
            v15 = v28;
            v9 = -2046820351;
            goto LABEL_36;
          }
          if ( a8 == 0xFFFFFFFFLL )
          {
            v19 = 0x7FFFFFFF;
            v20 = a7;
            do
            {
              if ( !*v20 )
                break;
              ++v20;
              --v19;
            }
            while ( v19 );
            v21 = 0x7FFFFFFF - v19;
            if ( !v19 )
              goto LABEL_35;
          }
          else
          {
            v21 = a8;
          }
          v22 = 0;
          while ( InvStrCmpNIW(a7, (&c_rgszCfgNodeDataType)[v22], v21) || (&c_rgszCfgNodeDataType)[v22][v21] )
          {
            v22 = (unsigned int)(v22 + 1);
            if ( (int)v22 >= 14 )
              goto LABEL_35;
          }
          LODWORD(v30) = v22;
        }
        else
        {
          EndPtr = 0;
          if ( !hMem )
          {
            v9 = -2147467261;
            goto LABEL_61;
          }
          if ( !*(_WORD *)hMem || (v23 = wcstoul((const wchar_t *)hMem, &EndPtr, 10), *EndPtr) )
          {
            v9 = -2147024809;
            goto LABEL_61;
          }
          LODWORD(v30) = v23;
        }
        v18 = v30;
      }
      v9 = CSyncMLMeta::SetPropertyEx(*(CSyncMLMeta **)&EventDescriptor.Id, v16, v18);
      if ( v9 >= 0 )
        goto LABEL_55;
    }
LABEL_61:
    LocalFree(v28);
    LocalFree(hMem);
    goto LABEL_62;
  }
  if ( (unsigned int)(v14 - 41) > 0x18 )
  {
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      *(_DWORD *)&v29.Level = 2;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      *(_DWORD *)&v29.Id = 184549376;
      v29.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v33 = (char *)qword_1800373C8;
      UserData.Reserved = 2;
      v34 = 33;
      v35 = 1;
      LODWORD(EndPtr) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v29, 0, 0, 2u, &UserData);
    }
LABEL_23:
    v9 = -2102788095;
    LocalFree(v28);
    LocalFree(hMem);
LABEL_62:
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      *(_DWORD *)&v29.Level = 2;
      UserData.Ptr = (ULONGLONG)off_18003E050;
      *(_DWORD *)&v29.Id = 184549376;
      v29.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_18003E050;
      v33 = (char *)&dword_18003741C;
      UserData.Reserved = 2;
      v34 = 27;
      v35 = 1;
      LODWORD(EndPtr) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v29, 0, 0, 2u, &UserData);
    }
    if ( *(int *)(*(_QWORD *)&EventDescriptor.Id + 132LL) >= 0 )
      *(_DWORD *)(*(_QWORD *)&EventDescriptor.Id + 132LL) = v9;
    goto LABEL_56;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v33 = byte_18003735B;
    UserData.Reserved = 2;
    v34 = 24;
    v35 = 1;
    LODWORD(EndPtr) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  v17 = v28;
  **(_DWORD **)&v29.Id = v14;
  LocalFree(v17);
  LocalFree(hMem);
  v9 = 0;
LABEL_56:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    LODWORD(EndPtr) = v9;
    p_EndPtr = &EndPtr;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v37 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v33 = (char *)word_18003749A;
    UserData.Reserved = 2;
    v34 = 23;
    v35 = 1;
    LODWORD(v30) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180021ae0  mov     r11, rsp
0x180021ae3  push    rbp
0x180021ae4  push    rbx
0x180021ae5  push    rsi
0x180021ae6  push    r13
0x180021ae8  lea     rbp, [r11-37h]
0x180021aec  sub     rsp, 0E8h
0x180021af3  mov     rax, cs:__security_cookie
0x180021afa  xor     rax, rsp
0x180021afd  mov     [rbp+2Fh+var_50], rax
0x180021b01  mov     rax, [rbp+2Fh+arg_40]
0x180021b05  mov     r10, r9
0x180021b08  mov     qword ptr [rbp+2Fh+var_A8.Id], rax
0x180021b0c  mov     r9d, r8d
0x180021b0f  mov     [r11-28h], rdi
0x180021b13  lea     rax, [rsp+100h+EndPtr]
0x180021b18  mov     [rsp+30h], rax
0x180021b1d  mov     r8, rdx
0x180021b20  mov     edx, [rbp+2Fh+arg_20]
0x180021b23  lea     rax, [rsp+100h+var_B0]
0x180021b28  mov     [r11-30h], r12
0x180021b2c  mov     r12, [rbp+2Fh+arg_30]
0x180021b30  mov     [rsp+100h+UserData], rax
0x180021b35  mov     eax, [rbp+2Fh+arg_28]
0x180021b38  mov     qword ptr [rbp+2Fh+EventDescriptor.Id], rcx
0x180021b3c  mov     rcx, r10
0x180021b3f  mov     [r11-38h], r14
0x180021b43  mov     [rsp+100h+UserDataCount], eax
0x180021b47  mov     [r11-40h], r15
0x180021b4b  mov     [rsp+100h+var_B0], 0
0x180021b54  mov     [rsp+100h+hMem], 0
0x180021b5d  mov     dword ptr [rsp+100h+EndPtr], 0
0x180021b65  call    ?CanonicalizeTag@@YAJPEBGK0KW4SyncMLElemType@@PEAPEAGPEAK@Z; CanonicalizeTag(ushort const *,ulong,ushort const *,ulong,SyncMLElemType,ushort * *,ulong *)
0x180021b6a  lea     r13, _TraceLoggingMetadataEnd
0x180021b71  mov     ebx, eax
0x180021b73  test    eax, eax
0x180021b75  js      loc_180022128
0x180021b7b  mov     rsi, [rsp+100h+var_B0]
0x180021b80  test    rsi, rsi
0x180021b83  jz      loc_180022116
0x180021b89  xor     eax, eax
0x180021b8b  cmp     ax, [rsi]
0x180021b8e  jz      loc_180022116
0x180021b94  mov     ebx, dword ptr [rsp+100h+EndPtr]
0x180021b98  mov     eax, 0FFFFFFFFh
0x180021b9d  mov     r15d, 7FFFFFFFh
0x180021ba3  cmp     rbx, rax
0x180021ba6  jnz     short loc_180021BD1
0x180021ba8  mov     ecx, r15d
0x180021bab  mov     rax, rsi
0x180021bae  xchg    ax, ax
0x180021bb0  cmp     word ptr [rax], 0
0x180021bb4  jz      short loc_180021BC0
0x180021bb6  add     rax, 2
0x180021bba  sub     rcx, 1
0x180021bbe  jnz     short loc_180021BB0
0x180021bc0  xor     eax, eax
0x180021bc2  mov     rbx, r15
0x180021bc5  sub     rbx, rcx
0x180021bc8  test    rcx, rcx
0x180021bcb  cmovz   rbx, rax
0x180021bcf  jz      short loc_180021C14
0x180021bd1  xor     edi, edi
0x180021bd3  lea     rcx, __ImageBase
0x180021bda  mov     r8, rbx
0x180021bdd  lea     r14, rva ?c_rgszSyncMLElem@@3PAPEBGA[rcx]; ushort const * near * c_rgszSyncMLElem ...
0x180021be4  mov     rcx, rsi
0x180021be7  mov     rdx, [r14+rdi*8]
0x180021beb  lea     r14, [r14+rdi*8]
0x180021bef  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x180021bf6  nop     dword ptr [rax+rax+00h]
0x180021bfb  test    eax, eax
0x180021bfd  jnz     short loc_180021C08
0x180021bff  mov     rcx, [r14]
0x180021c02  cmp     ax, [rcx+rbx*2]
0x180021c06  jz      short loc_180021C21
0x180021c08  inc     edi
0x180021c0a  cmp     edi, 49h ; 'I'
0x180021c0d  jl      short loc_180021BD3
0x180021c0f  mov     rsi, [rsp+100h+var_B0]
0x180021c14  mov     ebx, 82AA0001h
0x180021c19  mov     rcx, rsi
0x180021c1c  jmp     loc_180021E88
0x180021c21  cmp     edi, 17h
0x180021c24  jz      loc_180022003
0x180021c2a  mov     ecx, edi
0x180021c2c  call    ?SyncMLElemToPropIndex@CSyncMLMeta@@CAKW4SyncMLElemType@@@Z; CSyncMLMeta::SyncMLElemToPropIndex(SyncMLElemType)
0x180021c31  mov     r14d, eax
0x180021c34  mov     eax, 0FFFFFFFFh
0x180021c39  cmp     r14d, eax
0x180021c3c  jnz     loc_180021DEB
0x180021c42  lea     eax, [rdi-29h]
0x180021c45  cmp     eax, 18h
0x180021c48  mov     eax, cs:dword_18003E048
0x180021c4e  ja      loc_180021D21
0x180021c54  cmp     eax, 5
0x180021c57  jbe     loc_180021CEB
0x180021c5d  movzx   eax, cs:word_180037351
0x180021c64  lea     rsi, _TraceLoggingMetadata
0x180021c6b  mov     dword ptr [rbp+2Fh+EventDescriptor.Level], eax
0x180021c6e  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x180021c72  mov     rax, cs:off_18003E050
0x180021c79  xor     r9d, r9d; RelatedActivityId
0x180021c7c  mov     [rbp+2Fh+var_80.Ptr], rax
0x180021c80  xor     r8d, r8d; ActivityId
0x180021c83  mov     dword ptr [rbp+2Fh+EventDescriptor.Id], 0B000000h
0x180021c8a  mov     [rbp+2Fh+EventDescriptor.Keyword], 0
0x180021c92  movzx   eax, word ptr [rax]
0x180021c95  mov     [rbp+2Fh+var_80.Size], eax
0x180021c98  lea     rax, byte_18003735B
0x180021c9f  mov     [rbp+2Fh+var_70], rax
0x180021ca3  mov     rax, r13
0x180021ca6  sub     eax, esi
0x180021ca8  mov     dword ptr [rbp+2Fh+var_80.0Ch], 2
0x180021caf  mov     [rbp+2Fh+var_68], 18h
0x180021cb6  mov     [rbp+2Fh+var_64], 1
0x180021cbd  mov     dword ptr [rsp+100h+EndPtr], eax
0x180021cc1  mov     eax, dword ptr [rsp+100h+EndPtr]
0x180021cc5  mov     rcx, cs:RegHandle; RegHandle
0x180021ccc  lea     rax, [rbp+2Fh+var_80]
0x180021cd0  mov     [rsp+100h+UserData], rax; UserData
0x180021cd5  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x180021cdd  call    cs:__imp_EventWriteTransfer
0x180021ce4  nop     dword ptr [rax+rax+00h]
0x180021ce9  jmp     short loc_180021CF2
0x180021ceb  lea     rsi, _TraceLoggingMetadata
0x180021cf2  mov     rax, qword ptr [rbp+2Fh+var_A8.Id]
0x180021cf6  mov     rcx, [rsp+100h+var_B0]; hMem
0x180021cfb  mov     [rax], edi
0x180021cfd  call    cs:__imp_LocalFree
0x180021d04  nop     dword ptr [rax+rax+00h]
0x180021d09  mov     rcx, [rsp+100h+hMem]; hMem
0x180021d0e  call    cs:__imp_LocalFree
0x180021d15  nop     dword ptr [rax+rax+00h]
0x180021d1a  xor     ebx, ebx
0x180021d1c  jmp     loc_180022034
0x180021d21  cmp     eax, 2
0x180021d24  jbe     loc_180021DB8
0x180021d2a  movzx   eax, cs:word_1800373BE
0x180021d31  lea     rsi, _TraceLoggingMetadata
0x180021d38  mov     dword ptr [rbp+2Fh+var_A8.Level], eax
0x180021d3b  lea     rdx, [rbp+2Fh+var_A8]; EventDescriptor
0x180021d3f  mov     rax, cs:off_18003E050
0x180021d46  xor     r9d, r9d; RelatedActivityId
0x180021d49  mov     [rbp+2Fh+var_80.Ptr], rax
0x180021d4d  xor     r8d, r8d; ActivityId
0x180021d50  mov     dword ptr [rbp+2Fh+var_A8.Id], 0B000000h
0x180021d57  mov     [rbp+2Fh+var_A8.Keyword], 0
0x180021d5f  movzx   eax, word ptr [rax]
0x180021d62  mov     [rbp+2Fh+var_80.Size], eax
0x180021d65  lea     rax, qword_1800373C8
0x180021d6c  mov     [rbp+2Fh+var_70], rax
0x180021d70  mov     rax, r13
0x180021d73  sub     eax, esi
0x180021d75  mov     dword ptr [rbp+2Fh+var_80.0Ch], 2
0x180021d7c  mov     [rbp+2Fh+var_68], 21h ; '!'
0x180021d83  mov     [rbp+2Fh+var_64], 1
0x180021d8a  mov     dword ptr [rsp+100h+EndPtr], eax
0x180021d8e  mov     eax, dword ptr [rsp+100h+EndPtr]
0x180021d92  mov     rcx, cs:RegHandle; RegHandle
0x180021d99  lea     rax, [rbp+2Fh+var_80]
0x180021d9d  mov     [rsp+100h+UserData], rax; UserData
0x180021da2  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x180021daa  call    cs:__imp_EventWriteTransfer
0x180021db1  nop     dword ptr [rax+rax+00h]
0x180021db6  jmp     short loc_180021DBF
0x180021db8  lea     rsi, _TraceLoggingMetadata
0x180021dbf  mov     rcx, [rsp+100h+var_B0]; hMem
0x180021dc4  mov     ebx, 82AA0001h
0x180021dc9  call    cs:__imp_LocalFree
0x180021dd0  nop     dword ptr [rax+rax+00h]
0x180021dd5  mov     rcx, [rsp+100h+hMem]; hMem
0x180021dda  call    cs:__imp_LocalFree
0x180021de1  nop     dword ptr [rax+rax+00h]
0x180021de6  jmp     loc_180022159
0x180021deb  test    r12, r12
0x180021dee  jz      loc_180021F63
0x180021df4  xor     eax, eax
0x180021df6  cmp     ax, [r12]
0x180021dfb  jz      loc_180021F63
0x180021e01  mov     esi, [rbp+2Fh+arg_38]
0x180021e04  lea     r8, [rsp+100h+hMem]
0x180021e09  mov     edx, esi
0x180021e0b  mov     rcx, r12
0x180021e0e  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180021e15  nop     dword ptr [rax+rax+00h]
0x180021e1a  mov     ebx, eax
0x180021e1c  test    eax, eax
0x180021e1e  js      loc_180022128
0x180021e24  mov     rcx, [rsp+100h+hMem]; String
0x180021e29  mov     [rbp+2Fh+var_98], rcx
0x180021e2d  cmp     r14d, 4
0x180021e31  jbe     loc_180021F45
0x180021e37  cmp     edi, 2Ch ; ','
0x180021e3a  jnz     loc_180021EF4
0x180021e40  xor     eax, eax
0x180021e42  cmp     ax, [r12]
0x180021e47  jz      short loc_180021E7E
0x180021e49  mov     ecx, 0FFFFFFFFh
0x180021e4e  cmp     rsi, rcx
0x180021e51  jnz     short loc_180021EAA
0x180021e53  mov     rcx, r15
0x180021e56  mov     rax, r12
0x180021e59  nop     dword ptr [rax+00000000h]
0x180021e60  cmp     word ptr [rax], 0
0x180021e64  jz      short loc_180021E70
0x180021e66  add     rax, 2
0x180021e6a  sub     rcx, 1
0x180021e6e  jnz     short loc_180021E60
0x180021e70  sub     r15, rcx
0x180021e73  xor     eax, eax
0x180021e75  test    rcx, rcx
0x180021e78  cmovz   r15, rax
0x180021e7c  jnz     short loc_180021EAD
0x180021e7e  mov     rcx, [rsp+100h+var_B0]; hMem
0x180021e83  mov     ebx, 86000001h
0x180021e88  call    cs:__imp_LocalFree
0x180021e8f  nop     dword ptr [rax+rax+00h]
0x180021e94  mov     rcx, [rsp+100h+hMem]; hMem
0x180021e99  call    cs:__imp_LocalFree
0x180021ea0  nop     dword ptr [rax+rax+00h]
0x180021ea5  jmp     loc_180022152
0x180021eaa  mov     r15, rsi
0x180021ead  xor     ebx, ebx
0x180021eaf  nop
0x180021eb0  lea     rcx, __ImageBase
0x180021eb7  mov     r8, r15
0x180021eba  lea     rsi, rva ?c_rgszCfgNodeDataType@@3PAPEBGA[rcx]; ushort const * near * c_rgszCfgNodeDataType ...
0x180021ec1  mov     rcx, r12
0x180021ec4  mov     rdx, [rsi+rbx*8]
0x180021ec8  lea     rsi, [rsi+rbx*8]
0x180021ecc  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x180021ed3  nop     dword ptr [rax+rax+00h]
0x180021ed8  test    eax, eax
0x180021eda  jnz     short loc_180021EE6
0x180021edc  mov     rcx, [rsi]
0x180021edf  cmp     ax, [rcx+r15*2]
0x180021ee4  jz      short loc_180021EEF
0x180021ee6  inc     ebx
0x180021ee8  cmp     ebx, 0Eh
0x180021eeb  jl      short loc_180021EB0
0x180021eed  jmp     short loc_180021E7E
0x180021eef  mov     dword ptr [rbp+2Fh+var_98], ebx
0x180021ef2  jmp     short loc_180021F41
0x180021ef4  mov     [rsp+100h+EndPtr], 0
0x180021efd  test    rcx, rcx
0x180021f00  jnz     short loc_180021F0C
0x180021f02  mov     ebx, 80004003h
0x180021f07  jmp     loc_180022128
0x180021f0c  xor     eax, eax
0x180021f0e  cmp     ax, [rcx]
0x180021f11  jz      loc_180022123
0x180021f17  mov     r8d, 0Ah; Radix
0x180021f1d  lea     rdx, [rsp+100h+EndPtr]; EndPtr
0x180021f22  call    cs:__imp_wcstoul
0x180021f29  nop     dword ptr [rax+rax+00h]
0x180021f2e  mov     rcx, [rsp+100h+EndPtr]
0x180021f33  xor     edx, edx
0x180021f35  cmp     dx, [rcx]
0x180021f38  jnz     loc_180022123
0x180021f3e  mov     dword ptr [rbp+2Fh+var_98], eax
0x180021f41  mov     rcx, [rbp+2Fh+var_98]
0x180021f45  mov     r8, rcx; void *
0x180021f48  mov     edx, r14d; unsigned int
0x180021f4b  mov     rcx, qword ptr [rbp+2Fh+EventDescriptor.Id]; this
0x180021f4f  call    ?SetPropertyEx@CSyncMLMeta@@AEAAJKPEAX@Z; CSyncMLMeta::SetPropertyEx(ulong,void *)
0x180021f54  mov     ebx, eax
0x180021f56  test    eax, eax
0x180021f58  js      loc_180022128
0x180021f5e  jmp     loc_180022005
0x180021f63  mov     eax, cs:dword_18003E048
0x180021f69  cmp     eax, 2
0x180021f6c  jbe     loc_180021DB8
0x180021f72  movzx   eax, cs:word_180037439
0x180021f79  lea     rsi, _TraceLoggingMetadata
0x180021f80  mov     dword ptr [rbp+2Fh+var_A8.Level], eax
0x180021f83  lea     rdx, [rbp+2Fh+var_A8]; EventDescriptor
0x180021f87  mov     rax, cs:off_18003E050
0x180021f8e  xor     r9d, r9d; RelatedActivityId
0x180021f91  mov     [rbp+2Fh+var_80.Ptr], rax
0x180021f95  xor     r8d, r8d; ActivityId
0x180021f98  mov     dword ptr [rbp+2Fh+var_A8.Id], 0B000000h
0x180021f9f  mov     [rbp+2Fh+var_A8.Keyword], 0
0x180021fa7  movzx   eax, word ptr [rax]
0x180021faa  mov     [rbp+2Fh+var_80.Size], eax
0x180021fad  lea     rax, byte_180037443
0x180021fb4  mov     [rbp+2Fh+var_70], rax
0x180021fb8  mov     rax, r13
0x180021fbb  sub     eax, esi
0x180021fbd  mov     dword ptr [rbp+2Fh+var_80.0Ch], 2
0x180021fc4  mov     [rbp+2Fh+var_68], 11h
0x180021fcb  mov     [rbp+2Fh+var_64], 1
0x180021fd2  mov     dword ptr [rsp+100h+EndPtr], eax
0x180021fd6  mov     eax, dword ptr [rsp+100h+EndPtr]
0x180021fda  mov     rcx, cs:RegHandle; RegHandle
0x180021fe1  lea     rax, [rbp+2Fh+var_80]
0x180021fe5  mov     [rsp+100h+UserData], rax; UserData
0x180021fea  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x180021ff2  call    cs:__imp_EventWriteTransfer
0x180021ff9  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
