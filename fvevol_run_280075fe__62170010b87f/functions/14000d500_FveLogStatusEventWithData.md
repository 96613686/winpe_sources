# FveLogStatusEventWithData

- ea: `0x14000d500`
- end: `0x14000d79f`
- name: `FveLogStatusEventWithData`
- size: `671`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1400cb5b8`
- `0x1400cbcb4`
- `0x1400cca48`
- `0x1400cce60`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x14000110c`
- `0x14000d500`
- `0x1400218c0`
- `0x140021d00`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000d579`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000d579`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d592`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d592`
- `ntoskrnl!EtwWrite` at `0x14000d638`
- `ntoskrnl!EtwWrite` at `0x14000d638`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d772`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d772`

## pseudocode

```c
__int64 __fastcall FveLogStatusEventWithData(
        __int64 a1,
        __int64 a2,
        const EVENT_DESCRIPTOR *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  wchar_t *Buffer; // rdi
  unsigned __int16 MaximumLength; // bx
  NTSTATUS v13; // ebx
  REGHANDLE v14; // rcx
  __int16 v16; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+38h] [rbp-C8h] BYREF
  int Id; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+4Ch] [rbp-B4h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  int v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[6]; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+D0h] [rbp-30h] BYREF
  int *p_Id; // [rsp+F0h] [rbp-10h]
  __int64 v28; // [rsp+F8h] [rbp-8h]
  int *v29; // [rsp+100h] [rbp+0h]
  __int64 v30; // [rsp+108h] [rbp+8h]
  char v31[16]; // [rsp+110h] [rbp+10h] BYREF
  int *v32; // [rsp+120h] [rbp+20h]
  __int64 v33; // [rsp+128h] [rbp+28h]
  int *v34; // [rsp+130h] [rbp+30h]
  __int64 v35; // [rsp+138h] [rbp+38h]
  int *v36; // [rsp+140h] [rbp+40h]
  __int64 v37; // [rsp+148h] [rbp+48h]
  int *v38; // [rsp+150h] [rbp+50h]
  __int64 v39; // [rsp+158h] [rbp+58h]
  __int64 *v40; // [rsp+160h] [rbp+60h]
  __int64 v41; // [rsp+168h] [rbp+68h]
  int v42; // [rsp+1D8h] [rbp+D8h] BYREF

  v42 = a4;
  *(_QWORD *)&DosName.Length = 0x20000;
  v16 = 0;
  Buffer = (wchar_t *)&v16;
  DosName.Buffer = (wchar_t *)&v16;
  MaximumLength = 2;
  memset(UserData, 0, sizeof(UserData));
  if ( *(_QWORD *)(a1 + 88) )
  {
    if ( a2 )
    {
      if ( KeAreAllApcsDisabled() || IoVolumeDeviceToDosName(*(PVOID *)(a2 + 120), &DosName) >= 0 )
      {
        Buffer = DosName.Buffer;
        MaximumLength = DosName.MaximumLength;
      }
      else
      {
        Buffer = (wchar_t *)&v16;
        *(_DWORD *)&DosName.Length = 0x20000;
        DosName.Buffer = (wchar_t *)&v16;
      }
    }
    v14 = *(_QWORD *)(a1 + 88);
    UserData[0].Ptr = (ULONGLONG)&v42;
    UserData[1].Size = MaximumLength;
    *(_QWORD *)&UserData[0].Size = 4;
    UserData[2].Ptr = (ULONGLONG)&a5;
    UserData[1].Ptr = (ULONGLONG)Buffer;
    UserData[3].Ptr = (ULONGLONG)&a6;
    UserData[4].Ptr = (ULONGLONG)&a7;
    UserData[5].Ptr = (ULONGLONG)&a8;
    UserData[1].Reserved = 0;
    *(_QWORD *)&UserData[2].Size = 4;
    *(_QWORD *)&UserData[3].Size = 4;
    *(_QWORD *)&UserData[4].Size = 4;
    *(_QWORD *)&UserData[5].Size = 4;
    v13 = EtwWrite(v14, a3, 0, 6u, UserData);
    if ( v13 >= 0
      && v42 < 0
      && (unsigned int)dword_140045040 > 4
      && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
    {
      Id = a3->Id;
      p_Id = &Id;
      v19 = v42;
      v29 = &v19;
      v28 = 4;
      v30 = 4;
      tlgCreate1Sz_wchar_t(v31, DosName.Buffer);
      v32 = &v20;
      v21 = a6;
      v20 = a5;
      v34 = &v21;
      v22 = a7;
      v36 = &v22;
      v23 = a8;
      v38 = &v23;
      v40 = &v24;
      v33 = 4;
      v35 = 4;
      v37 = 4;
      v39 = 4;
      v24 = 0x1000000;
      v41 = 8;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140045040, (unsigned __int8 *)&word_14003BC36, 0, 0, 0xAu, &v26);
    }
    if ( (__int16 *)DosName.Buffer != &v16 )
      ExFreePoolWithTag(DosName.Buffer, 0);
  }
  else
  {
    return (unsigned int)-1073741816;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000d500  mov     [rsp-8+arg_18], r9d
0x14000d505  push    rbp
0x14000d506  push    rbx
0x14000d507  push    rsi
0x14000d508  push    rdi
0x14000d509  push    r12
0x14000d50b  push    r14
0x14000d50d  push    r15
0x14000d50f  lea     rbp, [rsp-80h]
0x14000d514  sub     rsp, 180h
0x14000d51b  mov     rax, cs:__security_cookie
0x14000d522  xor     rax, rsp
0x14000d525  mov     [rbp+0B0h+var_40], rax
0x14000d529  xor     r12d, r12d
0x14000d52c  mov     qword ptr [rsp+1B0h+DosName.Length], 20000h
0x14000d535  mov     r15, r8
0x14000d538  mov     [rsp+1B0h+var_180], r12w
0x14000d53e  mov     rsi, rdx
0x14000d541  lea     rdi, [rsp+1B0h+var_180]
0x14000d546  mov     r14, rcx
0x14000d549  mov     [rsp+1B0h+DosName.Buffer], rdi
0x14000d54e  lea     r8d, [r12+60h]; Size
0x14000d553  xor     edx, edx; Val
0x14000d555  lea     rcx, [rsp+1B0h+var_140]; void *
0x14000d55a  lea     ebx, [r12+2]
0x14000d55f  call    memset
0x14000d564  cmp     [r14+58h], r12
0x14000d568  jnz     short loc_14000D574
0x14000d56a  mov     ebx, 0C0000008h
0x14000d56f  jmp     loc_14000D77E
0x14000d574  test    rsi, rsi
0x14000d577  jz      short loc_14000D5C0
0x14000d579  call    cs:__imp_KeAreAllApcsDisabled
0x14000d580  nop     dword ptr [rax+rax+00h]
0x14000d585  test    al, al
0x14000d587  jnz     short loc_14000D5B6
0x14000d589  mov     rcx, [rsi+78h]; VolumeDeviceObject
0x14000d58d  lea     rdx, [rsp+1B0h+DosName]; DosName
0x14000d592  call    cs:__imp_IoVolumeDeviceToDosName
0x14000d599  nop     dword ptr [rax+rax+00h]
0x14000d59e  test    eax, eax
0x14000d5a0  jns     short loc_14000D5B6
0x14000d5a2  lea     rdi, [rsp+1B0h+var_180]
0x14000d5a7  mov     dword ptr [rsp+1B0h+DosName.Length], 20000h
0x14000d5af  mov     [rsp+1B0h+DosName.Buffer], rdi
0x14000d5b4  jmp     short loc_14000D5C0
0x14000d5b6  mov     rdi, [rsp+1B0h+DosName.Buffer]
0x14000d5bb  movzx   ebx, [rsp+1B0h+DosName.MaximumLength]
0x14000d5c0  mov     rcx, [r14+58h]; RegHandle
0x14000d5c4  lea     rax, [rbp+0B0h+arg_18]
0x14000d5cb  mov     [rsp+1B0h+var_140.Ptr], rax
0x14000d5d0  mov     esi, 4
0x14000d5d5  movzx   eax, bx
0x14000d5d8  xor     r8d, r8d; ActivityId
0x14000d5db  mov     [rbp+0B0h+var_128], eax
0x14000d5de  mov     rdx, r15; EventDescriptor
0x14000d5e1  lea     rax, [rbp+0B0h+arg_20]
0x14000d5e8  mov     qword ptr [rsp+1B0h+var_140.Size], rsi
0x14000d5ed  mov     [rbp+0B0h+var_120], rax
0x14000d5f1  lea     r9d, [rsi+2]; UserDataCount
0x14000d5f5  lea     rax, [rbp+0B0h+arg_28]
0x14000d5fc  mov     [rbp+0B0h+var_130], rdi
0x14000d600  mov     [rbp+0B0h+var_110], rax
0x14000d604  lea     rax, [rbp+0B0h+arg_30]
0x14000d60b  mov     [rbp+0B0h+var_100], rax
0x14000d60f  lea     rax, [rbp+0B0h+arg_38]
0x14000d616  mov     [rbp+0B0h+var_F0], rax
0x14000d61a  lea     rax, [rsp+1B0h+var_140]
0x14000d61f  mov     [rsp+1B0h+UserData], rax; UserData
0x14000d624  mov     [rbp+0B0h+var_124], r12d
0x14000d628  mov     [rbp+0B0h+var_118], rsi
0x14000d62c  mov     [rbp+0B0h+var_108], rsi
0x14000d630  mov     [rbp+0B0h+var_F8], rsi
0x14000d634  mov     [rbp+0B0h+var_E8], rsi
0x14000d638  call    cs:__imp_EtwWrite
0x14000d63f  nop     dword ptr [rax+rax+00h]
0x14000d644  mov     ebx, eax
0x14000d646  test    eax, eax
0x14000d648  js      loc_14000D761
0x14000d64e  cmp     [rbp+0B0h+arg_18], r12d
0x14000d655  jge     loc_14000D761
0x14000d65b  mov     ecx, cs:dword_140045040
0x14000d661  cmp     ecx, esi
0x14000d663  jbe     loc_14000D761
0x14000d669  mov     rdx, 400000000000h
0x14000d673  lea     rcx, dword_140045040
0x14000d67a  call    _tlgKeywordOn
0x14000d67f  test    al, al
0x14000d681  jz      loc_14000D761
0x14000d687  movzx   eax, word ptr [r15]
0x14000d68b  lea     rcx, [rbp+0B0h+var_A0]
0x14000d68f  mov     rdx, [rsp+1B0h+DosName.Buffer]
0x14000d694  mov     [rsp+1B0h+var_168], eax
0x14000d698  lea     rax, [rsp+1B0h+var_168]
0x14000d69d  mov     [rbp+0B0h+var_C0], rax
0x14000d6a1  mov     eax, [rbp+0B0h+arg_18]
0x14000d6a7  mov     [rsp+1B0h+var_164], eax
0x14000d6ab  lea     rax, [rsp+1B0h+var_164]
0x14000d6b0  mov     [rbp+0B0h+var_B0], rax
0x14000d6b4  mov     [rbp+0B0h+var_B8], rsi
0x14000d6b8  mov     [rbp+0B0h+var_A8], rsi
0x14000d6bc  call    _tlgCreate1Sz_wchar_t
0x14000d6c1  mov     ecx, [rbp+0B0h+arg_20]
0x14000d6c7  lea     rax, [rsp+1B0h+var_160]
0x14000d6cc  mov     [rbp+0B0h+var_90], rax
0x14000d6d0  lea     rdx, word_14003BC36
0x14000d6d7  mov     eax, [rbp+0B0h+arg_28]
0x14000d6dd  xor     r9d, r9d
0x14000d6e0  mov     [rsp+1B0h+var_15C], eax
0x14000d6e4  xor     r8d, r8d
0x14000d6e7  lea     rax, [rsp+1B0h+var_15C]
0x14000d6ec  mov     [rsp+1B0h+var_160], ecx
0x14000d6f0  mov     [rbp+0B0h+var_80], rax
0x14000d6f4  lea     rcx, dword_140045040
0x14000d6fb  mov     eax, [rbp+0B0h+arg_30]
0x14000d701  mov     [rsp+1B0h+var_158], eax
0x14000d705  lea     rax, [rsp+1B0h+var_158]
0x14000d70a  mov     [rbp+0B0h+var_70], rax
0x14000d70e  mov     eax, [rbp+0B0h+arg_38]
0x14000d714  mov     [rsp+1B0h+var_154], eax
0x14000d718  lea     rax, [rsp+1B0h+var_154]
0x14000d71d  mov     [rbp+0B0h+var_60], rax
0x14000d721  lea     rax, [rsp+1B0h+var_150]
0x14000d726  mov     [rbp+0B0h+var_50], rax
0x14000d72a  lea     rax, [rbp+0B0h+var_E0]
0x14000d72e  mov     [rsp+1B0h+var_188], rax
0x14000d733  mov     dword ptr [rsp+1B0h+UserData], 0Ah
0x14000d73b  mov     [rbp+0B0h+var_88], rsi
0x14000d73f  mov     [rbp+0B0h+var_78], rsi
0x14000d743  mov     [rbp+0B0h+var_68], rsi
0x14000d747  mov     [rbp+0B0h+var_58], rsi
0x14000d74b  mov     [rsp+1B0h+var_150], 1000000h
0x14000d754  mov     [rbp+0B0h+var_48], 8
0x14000d75c  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d761  mov     rcx, [rsp+1B0h+DosName.Buffer]; P
0x14000d766  lea     rax, [rsp+1B0h+var_180]
0x14000d76b  cmp     rcx, rax
0x14000d76e  jz      short loc_14000D77E
0x14000d770  xor     edx, edx; Tag
0x14000d772  call    cs:__imp_ExFreePoolWithTag
0x14000d779  nop     dword ptr [rax+rax+00h]
0x14000d77e  mov     eax, ebx
0x14000d780  mov     rcx, [rbp+0B0h+var_40]
0x14000d784  xor     rcx, rsp; StackCookie
0x14000d787  call    __security_check_cookie
0x14000d78c  add     rsp, 180h
0x14000d793  pop     r15
0x14000d795  pop     r14
0x14000d797  pop     r12
0x14000d799  pop     rdi
0x14000d79a  pop     rsi
0x14000d79b  pop     rbx
0x14000d79c  pop     rbp
0x14000d79d  retn
```
