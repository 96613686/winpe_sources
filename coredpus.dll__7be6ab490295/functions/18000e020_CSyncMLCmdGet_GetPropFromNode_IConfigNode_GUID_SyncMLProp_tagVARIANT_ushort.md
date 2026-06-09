# CSyncMLCmdGet::GetPropFromNode(IConfigNode *,_GUID,SyncMLProp,tagVARIANT *,ushort * *)

- ea: `0x18000e020`
- end: `0x18000e192`
- name: `?GetPropFromNode@CSyncMLCmdGet@@AEBAJPEAUIConfigNode@@U_GUID@@W4SyncMLProp@@PEAUtagVARIANT@@PEAPEAG@Z`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b560`
- `0x18000e1a0`

## callees

- `0x180003f70`
- `0x18000e020`
- `0x180014330`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e163`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e163`
- `DMCmnUtils!CopyString` at `0x18000e081`
- `DMCmnUtils!CopyString` at `0x18000e081`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdGet::GetPropFromNode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        VARIANTARG *a5,
        unsigned __int16 **a6)
{
  __int64 v6; // rbp
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax
  _DWORD v11[2]; // [rsp+30h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-50h] BYREF
  __int64 *v14; // [rsp+58h] [rbp-40h]
  int v15; // [rsp+60h] [rbp-38h]
  int v16; // [rsp+64h] [rbp-34h]
  _DWORD *v17; // [rsp+68h] [rbp-30h]
  __int64 v18; // [rsp+70h] [rbp-28h]

  v6 = a4;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)a2 + 160LL))(a2, a3, a5);
  v8 = v7;
  if ( v7 == -2147023728 )
  {
    v9 = CopyString(&word_180032B28, 0, a6);
  }
  else
  {
    if ( v7 < 0 )
      goto LABEL_6;
    v9 = ConformVariantToData(a5, *((_DWORD *)&gc_rgPropsToCfgDataType + v6), 1u, a6);
  }
  v8 = v9;
LABEL_6:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v11[0] = v8;
    EventDescriptor.Keyword = 0;
    v17 = v11;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v18 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v14 = qword_180036A18;
    UserData.Reserved = 2;
    v15 = 28;
    v16 = 1;
    v11[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return v8;
}

```

## disassembly

```asm
0x18000e020  mov     [rsp+arg_0], rbx
0x18000e025  push    rbp
0x18000e026  push    rsi
0x18000e027  push    rdi
0x18000e028  sub     rsp, 80h
0x18000e02f  mov     rax, cs:__security_cookie
0x18000e036  xor     rax, rsp
0x18000e039  mov     [rsp+98h+var_20], rax
0x18000e03e  mov     rax, [rdx]
0x18000e041  mov     r11, r8
0x18000e044  mov     rsi, [rsp+98h+arg_20]
0x18000e04c  mov     rcx, rdx
0x18000e04f  mov     rdi, [rsp+98h+arg_28]
0x18000e057  mov     r8, rsi
0x18000e05a  mov     rdx, r11
0x18000e05d  movsxd  rbp, r9d
0x18000e060  mov     rax, [rax+0A0h]
0x18000e067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e06c  mov     ebx, eax
0x18000e06e  cmp     eax, 80070490h
0x18000e073  jnz     short loc_18000E08F
0x18000e075  mov     r8, rdi
0x18000e078  lea     rcx, word_180032B28
0x18000e07f  xor     edx, edx
0x18000e081  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000e088  nop     dword ptr [rax+rax+00h]
0x18000e08d  jmp     short loc_18000E0AE
0x18000e08f  test    eax, eax
0x18000e091  js      short loc_18000E0B0
0x18000e093  lea     rax, ?gc_rgPropsToCfgDataType@@3QBW4ConfigDataType@@B; ConfigDataType const near * const gc_rgPropsToCfgDataType
0x18000e09a  mov     r9, rdi
0x18000e09d  mov     edx, [rax+rbp*4]
0x18000e0a0  mov     r8d, 1
0x18000e0a6  mov     rcx, rsi
0x18000e0a9  call    ?ConformVariantToData@@YAJPEAUtagVARIANT@@W4ConfigDataType@@KPEAPEAG@Z; ConformVariantToData(tagVARIANT *,ConfigDataType,ulong,ushort * *)
0x18000e0ae  mov     ebx, eax
0x18000e0b0  mov     eax, cs:dword_18003E048
0x18000e0b6  cmp     eax, 5
0x18000e0b9  jbe     loc_18000E16F
0x18000e0bf  xor     ecx, ecx
0x18000e0c1  mov     [rsp+98h+var_68], ebx
0x18000e0c5  mov     [rsp+98h+EventDescriptor.Keyword], rcx
0x18000e0ca  lea     rax, [rsp+98h+var_68]
0x18000e0cf  mov     [rsp+98h+var_30], rax
0x18000e0d4  lea     rcx, _TraceLoggingMetadata
0x18000e0db  movzx   eax, cs:word_180036A0E
0x18000e0e2  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x18000e0e7  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x18000e0eb  xor     r9d, r9d; RelatedActivityId
0x18000e0ee  mov     rax, cs:off_18003E050
0x18000e0f5  xor     r8d, r8d; ActivityId
0x18000e0f8  mov     [rsp+98h+var_50.Ptr], rax
0x18000e0fd  mov     [rsp+98h+var_28], 4
0x18000e106  mov     dword ptr [rsp+98h+EventDescriptor.Id], 0B000000h
0x18000e10e  movzx   eax, word ptr [rax]
0x18000e111  mov     [rsp+98h+var_50.Size], eax
0x18000e115  lea     rax, qword_180036A18
0x18000e11c  mov     [rsp+98h+var_40], rax
0x18000e121  lea     rax, _TraceLoggingMetadataEnd
0x18000e128  sub     eax, ecx
0x18000e12a  mov     dword ptr [rsp+98h+var_50.0Ch], 2
0x18000e132  mov     [rsp+98h+var_38], 1Ch
0x18000e13a  mov     [rsp+98h+var_34], 1
0x18000e142  mov     [rsp+98h+var_64], eax
0x18000e146  mov     eax, [rsp+98h+var_64]
0x18000e14a  mov     rcx, cs:RegHandle; RegHandle
0x18000e151  lea     rax, [rsp+98h+var_50]
0x18000e156  mov     [rsp+98h+UserData], rax; UserData
0x18000e15b  mov     [rsp+98h+UserDataCount], 3; UserDataCount
0x18000e163  call    cs:__imp_EventWriteTransfer
0x18000e16a  nop     dword ptr [rax+rax+00h]
0x18000e16f  mov     eax, ebx
0x18000e171  mov     rcx, [rsp+98h+var_20]
0x18000e176  xor     rcx, rsp; StackCookie
0x18000e179  call    __security_check_cookie
0x18000e17e  mov     rbx, [rsp+98h+arg_0]
0x18000e186  add     rsp, 80h
0x18000e18d  pop     rdi
0x18000e18e  pop     rsi
0x18000e18f  pop     rbp
0x18000e190  retn
```
