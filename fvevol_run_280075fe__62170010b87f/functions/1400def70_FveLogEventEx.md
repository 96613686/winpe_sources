# FveLogEventEx

- ea: `0x1400def70`
- end: `0x1400df1d4`
- name: `FveLogEventEx`
- size: `612`
- prototype: ``
- caller_count: `33`
- callee_count: `5`
- tags: ``

## callers

- `0x14006ae18`
- `0x14009c2c0`
- `0x14009e5e8`
- `0x14009ec2c`
- `0x1400a600c`
- `0x1400a6940`
- `0x1400a6ed8`
- `0x1400a7d94`
- `0x1400a812c`
- `0x1400a8530`
- `0x1400a8bb4`
- `0x1400a9158`
- `0x1400aa9c4`
- `0x1400aca3c`
- `0x1400ad2fc`
- `0x1400ae214`
- `0x1400af77c`
- `0x1400b03f0`
- `0x1400b0e3c`
- `0x1400b18dc`
- `0x1400b1bdc`
- `0x1400b2504`
- `0x1400b72d4`
- `0x1400b8c90`
- `0x1400bed8c`
- `0x1400c0380`
- `0x1400c5310`
- `0x1400c7558`
- `0x1400c9248`
- `0x1400de284`
- `0x1400e57c0`
- `0x1400e6418`
- `0x1400e75a8`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x14000110c`
- `0x1400218c0`
- `0x1400def70`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400deffd`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400deffd`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400df01d`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400df01d`
- `ntoskrnl!EtwWrite` at `0x1400df0a6`
- `ntoskrnl!EtwWrite` at `0x1400df0a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400df19e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400df19e`

## pseudocode

```c
__int64 __fastcall FveLogEventEx(__int64 a1, const EVENT_DESCRIPTOR **a2, char a3, char a4)
{
  wchar_t *Buffer; // rcx
  NTSTATUS v9; // edi
  unsigned __int16 MaximumLength; // r14
  __int64 v11; // rsi
  const EVENT_DESCRIPTOR *v12; // rdx
  NTSTATUS v13; // eax
  int v14; // ecx
  const EVENT_DESCRIPTOR *v15; // rax
  int Id; // ecx
  __int16 v18; // [rsp+30h] [rbp-A9h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+38h] [rbp-A1h] BYREF
  int v20; // [rsp+48h] [rbp-91h] BYREF
  int v21; // [rsp+4Ch] [rbp-8Dh] BYREF
  int v22; // [rsp+50h] [rbp-89h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-81h] BYREF
  __int128 v24; // [rsp+68h] [rbp-71h]
  __int128 v25; // [rsp+78h] [rbp-61h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+90h] [rbp-49h] BYREF
  char v27[16]; // [rsp+B0h] [rbp-29h] BYREF
  int *v28; // [rsp+C0h] [rbp-19h]
  __int64 v29; // [rsp+C8h] [rbp-11h]
  int *v30; // [rsp+D0h] [rbp-9h]
  __int64 v31; // [rsp+D8h] [rbp-1h]
  int *v32; // [rsp+E0h] [rbp+7h]
  __int64 v33; // [rsp+E8h] [rbp+Fh]

  *(_QWORD *)&DosName.Length = 0x20000;
  Buffer = (wchar_t *)&v18;
  v18 = 0;
  DosName.Buffer = (wchar_t *)&v18;
  v9 = 0;
  MaximumLength = 2;
  UserData = 0;
  v24 = 0;
  v25 = 0;
  if ( a1 )
  {
    v11 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL);
    if ( v11 )
    {
      if ( *(_QWORD *)(v11 + 88) )
      {
        if ( KeAreAllApcsDisabled()
          || (v9 = IoVolumeDeviceToDosName(*(PVOID *)(*(_QWORD *)(a1 + 64) + 120LL), &DosName), v9 >= 0) )
        {
          Buffer = DosName.Buffer;
          MaximumLength = DosName.MaximumLength;
        }
        else
        {
          Buffer = (wchar_t *)&v18;
          *(_DWORD *)&DosName.Length = 0x20000;
          DosName.Buffer = (wchar_t *)&v18;
        }
        if ( a4 || *((int *)a2 + 3) < 0 )
        {
          v12 = *a2;
          UserData.Ptr = (ULONGLONG)a2 + 12;
          *((_QWORD *)&v24 + 1) = MaximumLength;
          *(_QWORD *)&v25 = a2 + 1;
          *(_QWORD *)&UserData.Size = 4;
          *(_QWORD *)&v24 = Buffer;
          *((_QWORD *)&v25 + 1) = 4;
          v13 = EtwWrite(*(_QWORD *)(v11 + 88), v12, 0, 3u, &UserData);
          Buffer = DosName.Buffer;
          v9 = v13;
        }
      }
    }
  }
  if ( a2 && *a2 && (a3 || *((int *)a2 + 3) < 0) )
  {
    if ( (unsigned int)dword_140045040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
    {
      tlgCreate1Sz_wchar_t(v27, DosName.Buffer);
      v14 = *((_DWORD *)a2 + 3);
      v28 = &v20;
      v15 = *a2;
      v20 = v14;
      v29 = 4;
      Id = v15->Id;
      v30 = &v21;
      v22 = *((_DWORD *)a2 + 2);
      v32 = &v22;
      v21 = Id;
      v31 = 4;
      v33 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140045040, (unsigned __int8 *)word_14003BCC2, 0, 0, 6u, &v26);
    }
    Buffer = DosName.Buffer;
  }
  if ( Buffer != (wchar_t *)&v18 )
    ExFreePoolWithTag(Buffer, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400def70  mov     [rsp-8+arg_10], rbx
0x1400def75  push    rbp
0x1400def76  push    rsi
0x1400def77  push    rdi
0x1400def78  push    r12
0x1400def7a  push    r13
0x1400def7c  push    r14
0x1400def7e  push    r15
0x1400def80  lea     rbp, [rsp-27h]
0x1400def85  sub     rsp, 100h
0x1400def8c  mov     rax, cs:__security_cookie
0x1400def93  xor     rax, rsp
0x1400def96  mov     [rbp+57h+var_40], rax
0x1400def9a  xorps   xmm0, xmm0
0x1400def9d  mov     qword ptr [rsp+130h+DosName.Length], 20000h
0x1400defa6  mov     r15, rcx
0x1400defa9  mov     r12b, r9b
0x1400defac  xor     r9d, r9d
0x1400defaf  lea     rcx, [rsp+130h+var_100]
0x1400defb4  mov     [rsp+130h+var_100], r9w
0x1400defba  mov     r13b, r8b
0x1400defbd  mov     [rsp+130h+DosName.Buffer], rcx
0x1400defc2  mov     rbx, rdx
0x1400defc5  mov     edi, r9d
0x1400defc8  lea     r14d, [r9+2]
0x1400defcc  movups  xmmword ptr [rsp+130h+var_D8.Ptr], xmm0
0x1400defd1  movups  [rbp+57h+var_C8], xmm0
0x1400defd5  movups  [rbp+57h+var_B8], xmm0
0x1400defd9  test    r15, r15
0x1400defdc  jz      loc_1400DF0BC
0x1400defe2  mov     rax, [r15+40h]
0x1400defe6  mov     rsi, [rax+8]
0x1400defea  test    rsi, rsi
0x1400defed  jz      loc_1400DF0BC
0x1400deff3  cmp     [rsi+58h], r9
0x1400deff7  jz      loc_1400DF0BC
0x1400deffd  call    cs:__imp_KeAreAllApcsDisabled
0x1400df004  nop     dword ptr [rax+rax+00h]
0x1400df009  xor     r9d, r9d
0x1400df00c  test    al, al
0x1400df00e  jnz     short loc_1400DF046
0x1400df010  mov     rcx, [r15+40h]
0x1400df014  lea     rdx, [rsp+130h+DosName]; DosName
0x1400df019  mov     rcx, [rcx+78h]; VolumeDeviceObject
0x1400df01d  call    cs:__imp_IoVolumeDeviceToDosName
0x1400df024  nop     dword ptr [rax+rax+00h]
0x1400df029  xor     r9d, r9d
0x1400df02c  mov     edi, eax
0x1400df02e  test    eax, eax
0x1400df030  jns     short loc_1400DF046
0x1400df032  lea     rcx, [rsp+130h+var_100]
0x1400df037  mov     dword ptr [rsp+130h+DosName.Length], 20000h
0x1400df03f  mov     [rsp+130h+DosName.Buffer], rcx
0x1400df044  jmp     short loc_1400DF051
0x1400df046  mov     rcx, [rsp+130h+DosName.Buffer]
0x1400df04b  movzx   r14d, [rsp+130h+DosName.MaximumLength]
0x1400df051  test    r12b, r12b
0x1400df054  jnz     short loc_1400DF05C
0x1400df056  cmp     [rbx+0Ch], r9d
0x1400df05a  jge     short loc_1400DF0BC
0x1400df05c  mov     rdx, [rbx]; EventDescriptor
0x1400df05f  lea     rax, [rbx+0Ch]
0x1400df063  mov     [rsp+130h+var_D8.Ptr], rax
0x1400df068  xor     r8d, r8d; ActivityId
0x1400df06b  mov     dword ptr [rbp+57h+var_C8+0Ch], r9d
0x1400df06f  mov     r9d, 3; UserDataCount
0x1400df075  movzx   eax, r14w
0x1400df079  mov     dword ptr [rbp+57h+var_C8+8], eax
0x1400df07c  lea     rax, [rbx+8]
0x1400df080  mov     qword ptr [rbp+57h+var_B8], rax
0x1400df084  lea     rax, [rsp+130h+var_D8]
0x1400df089  mov     qword ptr [rbp+57h+var_D8.Size], 4
0x1400df091  mov     qword ptr [rbp+57h+var_C8], rcx
0x1400df095  mov     qword ptr [rbp+57h+var_B8+8], 4
0x1400df09d  mov     rcx, [rsi+58h]; RegHandle
0x1400df0a1  mov     [rsp+130h+UserData], rax; UserData
0x1400df0a6  call    cs:__imp_EtwWrite
0x1400df0ad  nop     dword ptr [rax+rax+00h]
0x1400df0b2  mov     rcx, [rsp+130h+DosName.Buffer]
0x1400df0b7  xor     r9d, r9d
0x1400df0ba  mov     edi, eax
0x1400df0bc  test    rbx, rbx
0x1400df0bf  jz      loc_1400DF192
0x1400df0c5  cmp     [rbx], r9
0x1400df0c8  jz      loc_1400DF192
0x1400df0ce  test    r13b, r13b
0x1400df0d1  jnz     short loc_1400DF0DD
0x1400df0d3  cmp     [rbx+0Ch], r9d
0x1400df0d7  jge     loc_1400DF192
0x1400df0dd  mov     eax, cs:dword_140045040
0x1400df0e3  cmp     eax, 4
0x1400df0e6  jbe     loc_1400DF18D
0x1400df0ec  mov     rdx, 400000000000h
0x1400df0f6  lea     rcx, dword_140045040
0x1400df0fd  call    _tlgKeywordOn
0x1400df102  test    al, al
0x1400df104  jz      loc_1400DF18D
0x1400df10a  mov     rdx, [rsp+130h+DosName.Buffer]
0x1400df10f  lea     rcx, [rbp+57h+var_80]
0x1400df113  call    _tlgCreate1Sz_wchar_t
0x1400df118  mov     ecx, [rbx+0Ch]
0x1400df11b  lea     rax, [rsp+130h+var_E8]
0x1400df120  mov     [rbp+57h+var_70], rax
0x1400df124  lea     rdx, word_14003BCC2
0x1400df12b  mov     rax, [rbx]
0x1400df12e  xor     r9d, r9d
0x1400df131  mov     [rsp+130h+var_E8], ecx
0x1400df135  xor     r8d, r8d
0x1400df138  mov     [rbp+57h+var_68], 4
0x1400df140  movzx   ecx, word ptr [rax]
0x1400df143  lea     rax, [rsp+130h+var_E4]
0x1400df148  mov     [rbp+57h+var_60], rax
0x1400df14c  mov     eax, [rbx+8]
0x1400df14f  mov     [rsp+130h+var_E0], eax
0x1400df153  lea     rax, [rsp+130h+var_E0]
0x1400df158  mov     [rbp+57h+var_50], rax
0x1400df15c  lea     rax, [rbp+57h+var_A0]
0x1400df160  mov     [rsp+130h+var_E4], ecx
0x1400df164  lea     rcx, dword_140045040
0x1400df16b  mov     [rsp+130h+var_108], rax
0x1400df170  mov     dword ptr [rsp+130h+UserData], 6
0x1400df178  mov     [rbp+57h+var_58], 4
0x1400df180  mov     [rbp+57h+var_48], 4
0x1400df188  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400df18d  mov     rcx, [rsp+130h+DosName.Buffer]; P
0x1400df192  lea     rax, [rsp+130h+var_100]
0x1400df197  cmp     rcx, rax
0x1400df19a  jz      short loc_1400DF1AA
0x1400df19c  xor     edx, edx; Tag
0x1400df19e  call    cs:__imp_ExFreePoolWithTag
0x1400df1a5  nop     dword ptr [rax+rax+00h]
0x1400df1aa  mov     eax, edi
0x1400df1ac  mov     rcx, [rbp+57h+var_40]
0x1400df1b0  xor     rcx, rsp; StackCookie
0x1400df1b3  call    __security_check_cookie
0x1400df1b8  mov     rbx, [rsp+130h+arg_10]
0x1400df1c0  add     rsp, 100h
0x1400df1c7  pop     r15
0x1400df1c9  pop     r14
0x1400df1cb  pop     r13
0x1400df1cd  pop     r12
0x1400df1cf  pop     rdi
0x1400df1d0  pop     rsi
0x1400df1d1  pop     rbp
0x1400df1d2  retn
```
