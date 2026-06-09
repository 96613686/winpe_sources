# I_CollectCertsUsingCng

- ea: `0x180010d90`
- end: `0x180011188`
- name: `I_CollectCertsUsingCng`
- size: `1016`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005e10`

## callees

- `0x180004600`
- `0x180009c00`
- `0x18000a050`
- `0x180010d90`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x18001f548`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180010e22`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180010e31`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011100`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180010e22`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180010e31`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011100`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010ec5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800110f1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010ec5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800110f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010eef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010eef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011038`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011038`
- `ncrypt!NCryptFreeObject` at `0x180011012`
- `ncrypt!NCryptFreeObject` at `0x180011012`

## pseudocode

```c
__int64 __fastcall I_CollectCertsUsingCng(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx
  _WORD *v8; // rsi
  __int64 v9; // rcx
  STRSAFE_LPSTR v10; // rcx
  int v11; // edx
  __int64 v12; // rcx
  NCRYPT_HANDLE v13; // rcx
  __int64 v14; // rcx
  unsigned int v16; // [rsp+30h] [rbp-79h] BYREF
  _WORD *v17; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-61h] BYREF
  GUID ActivityId; // [rsp+58h] [rbp-51h] BYREF
  GUID v21; // [rsp+68h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-29h] BYREF
  __int16 *v23; // [rsp+90h] [rbp-19h]
  int v24; // [rsp+98h] [rbp-11h]
  int v25; // [rsp+9Ch] [rbp-Dh]
  unsigned int *v26; // [rsp+A0h] [rbp-9h]
  __int64 v27; // [rsp+A8h] [rbp-1h]
  unsigned int *v28; // [rsp+B0h] [rbp+7h]
  __int64 v29; // [rsp+B8h] [rbp+Fh]

  v17 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v21 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v21);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_180031010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v23 = &word_180029F0E;
    UserData.Reserved = 2;
    v24 = 32;
    v25 = 1;
    v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v21, &ActivityId, 2u, &UserData);
  }
  if ( !(unsigned int)I_GetDefaultCngContainer(a2, &v17) )
  {
    v8 = v17;
LABEL_15:
    if ( *(_QWORD *)(a2 + 80) )
    {
      v6 = I_ReaderListCngPopulateCredsViaContainerEnumeration(a1, v8, a2, a3);
      if ( !v6 )
        goto LABEL_28;
      WppTraceIndent(v9, 2);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_28;
      }
      v11 = 157;
    }
    else
    {
      v6 = I_ReaderListCngPopulateCredsViaCertStore(a1, v8, a2, a3);
      if ( !v6 )
        goto LABEL_28;
      v6 = I_ReaderListCngPopulateCredsViaContainerEnumeration(a1, v8, a2, a3);
      if ( !v6 )
        goto LABEL_28;
      WppTraceIndent(v12, 2);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_28;
      }
      v11 = 158;
    }
    WPP_SF_sD(
      *((_QWORD *)v10 + 2),
      v11,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v6);
    goto LABEL_28;
  }
  v6 = 8;
  v8 = HeapAlloc(hHeap, 8u, 2u);
  if ( v8 )
  {
    *v8 = 0;
    goto LABEL_15;
  }
  WppTraceIndent(v7, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
LABEL_28:
  v13 = *(_QWORD *)(a2 + 136);
  if ( v13 )
  {
    NCryptFreeObject(v13);
    *(_QWORD *)(a2 + 136) = 0;
  }
  if ( v8 )
    HeapFree(hHeap, 0, v8);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    v16 = *a3;
    v27 = 4;
    v26 = &v16;
    v18 = v6;
    v28 = &v18;
    *(_DWORD *)&EventDescriptor.Level = 517;
    UserData.Ptr = (ULONGLONG)off_180031010;
    v29 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v23 = (__int16 *)&dword_18002A9EC;
    UserData.Reserved = 2;
    v24 = 60;
    v25 = 1;
    LODWORD(v17) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v21, &ActivityId, 4u, &UserData);
  }
  EventActivityIdControl(2u, &ActivityId);
  if ( !v6 )
  {
    *(_DWORD *)(a2 + 216) = *a3;
    *(_DWORD *)(a2 + 224) = 3;
  }
  WppTraceIndent(v14, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      159,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180010d90  mov     [rsp-8+arg_18], rbx
0x180010d95  push    rbp
0x180010d96  push    rsi
0x180010d97  push    rdi
0x180010d98  push    r12
0x180010d9a  push    r13
0x180010d9c  push    r14
0x180010d9e  push    r15
0x180010da0  lea     rbp, [rsp-27h]
0x180010da5  sub     rsp, 0D0h
0x180010dac  mov     rax, cs:__security_cookie
0x180010db3  xor     rax, rsp
0x180010db6  mov     [rbp+57h+var_40], rax
0x180010dba  mov     rdi, rdx
0x180010dbd  xor     ebx, ebx
0x180010dbf  xor     edx, edx
0x180010dc1  mov     [rbp+57h+var_C8], rbx
0x180010dc5  mov     r15, r8
0x180010dc8  mov     r14, rcx
0x180010dcb  call    WppTraceIndent
0x180010dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010dd7  lea     r13, WPP_GLOBAL_Control
0x180010dde  cmp     rcx, r13
0x180010de1  jz      short loc_180010E0B
0x180010de3  test    byte ptr [rcx+1Ch], 2
0x180010de7  jz      short loc_180010E0B
0x180010de9  cmp     byte ptr [rcx+19h], 5
0x180010ded  jb      short loc_180010E0B
0x180010def  mov     r9, cs:WPP_pszIndent
0x180010df6  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180010dfd  mov     rcx, [rcx+10h]
0x180010e01  mov     edx, 9Bh
0x180010e06  call    WPP_SF_s
0x180010e0b  xorps   xmm0, xmm0
0x180010e0e  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180010e12  xorps   xmm1, xmm1
0x180010e15  mov     ecx, 5; ControlCode
0x180010e1a  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180010e1e  movups  xmmword ptr [rbp+57h+var_98.Data1], xmm1
0x180010e22  call    cs:__imp_EventActivityIdControl
0x180010e28  lea     rdx, [rbp+57h+var_98]; ActivityId
0x180010e2c  mov     ecx, 1; ControlCode
0x180010e31  call    cs:__imp_EventActivityIdControl
0x180010e37  mov     eax, cs:dword_180031008
0x180010e3d  lea     r12, _TraceLoggingMetadataEnd
0x180010e44  lea     rcx, _TraceLoggingMetadata
0x180010e4b  cmp     eax, 5
0x180010e4e  jbe     short loc_180010ECB
0x180010e50  movzx   eax, cs:word_180029F04
0x180010e57  lea     r9, [rbp+57h+ActivityId]; RelatedActivityId
0x180010e5b  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180010e5e  lea     r8, [rbp+57h+var_98]; ActivityId
0x180010e62  mov     rax, cs:off_180031010
0x180010e69  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180010e6d  mov     [rbp+57h+var_80.Ptr], rax
0x180010e71  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180010e78  mov     [rbp+57h+EventDescriptor.Keyword], rbx
0x180010e7c  movzx   eax, word ptr [rax]
0x180010e7f  mov     [rbp+57h+var_80.Size], eax
0x180010e82  lea     rax, word_180029F0E
0x180010e89  mov     [rbp+57h+var_70], rax
0x180010e8d  mov     rax, r12
0x180010e90  sub     eax, ecx
0x180010e92  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180010e99  mov     [rbp+57h+var_68], 20h ; ' '
0x180010ea0  mov     [rbp+57h+var_64], 1
0x180010ea7  mov     [rbp+57h+var_D0], eax
0x180010eaa  mov     eax, [rbp+57h+var_D0]
0x180010ead  mov     rcx, cs:RegHandle; RegHandle
0x180010eb4  lea     rax, [rbp+57h+var_80]
0x180010eb8  mov     [rsp+100h+UserData], rax; UserData
0x180010ebd  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x180010ec5  call    cs:__imp_EventWriteTransfer
0x180010ecb  lea     rdx, [rbp+57h+var_C8]
0x180010ecf  mov     rcx, rdi
0x180010ed2  call    I_GetDefaultCngContainer
0x180010ed7  test    eax, eax
0x180010ed9  jz      short loc_180010F53
0x180010edb  mov     rcx, cs:hHeap; hHeap
0x180010ee2  mov     ebx, 8
0x180010ee7  mov     edx, ebx; dwFlags
0x180010ee9  mov     r8d, 2; dwBytes
0x180010eef  call    cs:__imp_HeapAlloc
0x180010ef5  mov     rsi, rax
0x180010ef8  test    rax, rax
0x180010efb  jnz     short loc_180010F4C
0x180010efd  mov     edx, 2
0x180010f02  call    WppTraceIndent
0x180010f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f0e  cmp     rcx, r13
0x180010f11  jz      loc_180011006
0x180010f17  test    byte ptr [rcx+1Ch], 1
0x180010f1b  jz      loc_180011006
0x180010f21  cmp     byte ptr [rcx+19h], 2
0x180010f25  jb      loc_180011006
0x180010f2b  mov     r9, cs:WPP_pszIndent
0x180010f32  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180010f39  mov     rcx, [rcx+10h]
0x180010f3d  mov     edx, 9Ch
0x180010f42  call    WPP_SF_s
0x180010f47  jmp     loc_180011006
0x180010f4c  xor     eax, eax
0x180010f4e  mov     [rsi], ax
0x180010f51  jmp     short loc_180010F57
0x180010f53  mov     rsi, [rbp+57h+var_C8]
0x180010f57  cmp     qword ptr [rdi+50h], 0
0x180010f5c  mov     r9, r15
0x180010f5f  mov     r8, rdi
0x180010f62  mov     rdx, rsi
0x180010f65  mov     rcx, r14
0x180010f68  jz      short loc_180010FA2
0x180010f6a  call    I_ReaderListCngPopulateCredsViaContainerEnumeration
0x180010f6f  mov     ebx, eax
0x180010f71  test    eax, eax
0x180010f73  jz      loc_180011006
0x180010f79  mov     edx, 2
0x180010f7e  call    WppTraceIndent
0x180010f83  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f8a  cmp     rcx, r13
0x180010f8d  jz      short loc_180011006
0x180010f8f  test    byte ptr [rcx+1Ch], 1
0x180010f93  jz      short loc_180011006
0x180010f95  cmp     byte ptr [rcx+19h], 2
0x180010f99  jb      short loc_180011006
0x180010f9b  mov     edx, 9Dh
0x180010fa0  jmp     short loc_180010FEB
0x180010fa2  call    I_ReaderListCngPopulateCredsViaCertStore
0x180010fa7  mov     ebx, eax
0x180010fa9  test    eax, eax
0x180010fab  jz      short loc_180011006
0x180010fad  mov     r9, r15
0x180010fb0  mov     r8, rdi
0x180010fb3  mov     rdx, rsi
0x180010fb6  mov     rcx, r14
0x180010fb9  call    I_ReaderListCngPopulateCredsViaContainerEnumeration
0x180010fbe  mov     ebx, eax
0x180010fc0  test    eax, eax
0x180010fc2  jz      short loc_180011006
0x180010fc4  mov     edx, 2
0x180010fc9  call    WppTraceIndent
0x180010fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fd5  cmp     rcx, r13
0x180010fd8  jz      short loc_180011006
0x180010fda  test    byte ptr [rcx+1Ch], 1
0x180010fde  jz      short loc_180011006
0x180010fe0  cmp     byte ptr [rcx+19h], 2
0x180010fe4  jb      short loc_180011006
0x180010fe6  mov     edx, 9Eh
0x180010feb  mov     r9, cs:WPP_pszIndent
0x180010ff2  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180010ff9  mov     rcx, [rcx+10h]
0x180010ffd  mov     [rsp+100h+UserDataCount], ebx
0x180011001  call    WPP_SF_sD
0x180011006  mov     rcx, [rdi+88h]; hObject
0x18001100d  test    rcx, rcx
0x180011010  jz      short loc_180011024
0x180011012  call    cs:__imp_NCryptFreeObject
0x180011018  xor     r14d, r14d
0x18001101b  mov     [rdi+88h], r14
0x180011022  jmp     short loc_180011027
0x180011024  xor     r14d, r14d
0x180011027  test    rsi, rsi
0x18001102a  jz      short loc_18001103E
0x18001102c  mov     rcx, cs:hHeap; hHeap
0x180011033  mov     r8, rsi; lpMem
0x180011036  xor     edx, edx; dwFlags
0x180011038  call    cs:__imp_HeapFree
0x18001103e  mov     eax, cs:dword_180031008
0x180011044  cmp     eax, 5
0x180011047  jbe     loc_1800110F7
0x18001104d  mov     eax, [r15]
0x180011050  lea     r9, [rbp+57h+ActivityId]; RelatedActivityId
0x180011054  mov     [rbp+57h+var_D0], eax
0x180011057  lea     r8, [rbp+57h+var_98]; ActivityId
0x18001105b  mov     [rbp+57h+var_58], 4
0x180011063  lea     rax, [rbp+57h+var_D0]
0x180011067  mov     [rbp+57h+var_60], rax
0x18001106b  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001106f  lea     rax, [rbp+57h+var_C0]
0x180011073  mov     [rbp+57h+var_C0], ebx
0x180011076  mov     [rbp+57h+var_50], rax
0x18001107a  movzx   eax, cs:word_18002A9E2
0x180011081  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180011084  mov     rax, cs:off_180031010
0x18001108b  mov     [rbp+57h+var_80.Ptr], rax
0x18001108f  mov     [rbp+57h+var_48], 4
0x180011097  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18001109e  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x1800110a2  movzx   eax, word ptr [rax]
0x1800110a5  mov     [rbp+57h+var_80.Size], eax
0x1800110a8  lea     rax, dword_18002A9EC
0x1800110af  mov     [rbp+57h+var_70], rax
0x1800110b3  lea     rax, _TraceLoggingMetadata
0x1800110ba  sub     r12d, eax
0x1800110bd  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x1800110c4  mov     [rbp+57h+var_68], 3Ch ; '<'
0x1800110cb  mov     [rbp+57h+var_64], 1
0x1800110d2  mov     dword ptr [rbp+57h+var_C8], r12d
0x1800110d6  mov     eax, dword ptr [rbp+57h+var_C8]
0x1800110d9  mov     rcx, cs:RegHandle; RegHandle
0x1800110e0  lea     rax, [rbp+57h+var_80]
0x1800110e4  mov     [rsp+100h+UserData], rax; UserData
0x1800110e9  mov     [rsp+100h+UserDataCount], 4; UserDataCount
0x1800110f1  call    cs:__imp_EventWriteTransfer
0x1800110f7  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800110fb  mov     ecx, 2; ControlCode
0x180011100  call    cs:__imp_EventActivityIdControl
0x180011106  test    ebx, ebx
0x180011108  jnz     short loc_18001111D
0x18001110a  mov     eax, [r15]
0x18001110d  mov     [rdi+0D8h], eax
0x180011113  mov     dword ptr [rdi+0E0h], 3
0x18001111d  mov     edx, 1
0x180011122  call    WppTraceIndent
0x180011127  mov     rcx, cs:WPP_GLOBAL_Control
0x18001112e  cmp     rcx, r13
0x180011131  jz      short loc_18001115F
0x180011133  test    byte ptr [rcx+1Ch], 2
0x180011137  jz      short loc_18001115F
0x180011139  cmp     byte ptr [rcx+19h], 5
0x18001113d  jb      short loc_18001115F
0x18001113f  mov     r9, cs:WPP_pszIndent
0x180011146  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001114d  mov     rcx, [rcx+10h]
0x180011151  mov     edx, 9Fh
0x180011156  mov     [rsp+100h+UserDataCount], ebx
0x18001115a  call    WPP_SF_sD
0x18001115f  mov     eax, ebx
0x180011161  mov     rcx, [rbp+57h+var_40]
0x180011165  xor     rcx, rsp; StackCookie
0x180011168  call    __security_check_cookie
0x18001116d  mov     rbx, [rsp+100h+arg_18]
0x180011175  add     rsp, 0D0h
0x18001117c  pop     r15
0x18001117e  pop     r14
0x180011180  pop     r13
0x180011182  pop     r12
0x180011184  pop     rdi
0x180011185  pop     rsi
0x180011186  pop     rbp
0x180011187  retn
```
