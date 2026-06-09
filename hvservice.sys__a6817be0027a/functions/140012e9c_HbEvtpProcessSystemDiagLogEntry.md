# HbEvtpProcessSystemDiagLogEntry

- ea: `0x140012e9c`
- end: `0x14001306d`
- name: `HbEvtpProcessSystemDiagLogEntry`
- size: `465`
- prototype: `int __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012c40`

## callees

- `0x140001070`
- `0x140002ae0`
- `0x140012e9c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140012feb`
- `ntoskrnl!EtwWrite` at `0x140012feb`

## pseudocode

```c
int __fastcall HbEvtpProcessSystemDiagLogEntry(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // edx
  __int64 v5; // rcx
  char *v6; // r10
  char *v7; // r9
  int result; // eax
  unsigned __int8 *v9; // rdx
  PVOID v10; // [rsp+30h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-31h] BYREF
  char *v13; // [rsp+58h] [rbp-21h]
  __int64 v14; // [rsp+60h] [rbp-19h]
  char *v15; // [rsp+68h] [rbp-11h]
  unsigned int v16; // [rsp+70h] [rbp-9h]
  int v17; // [rsp+74h] [rbp-5h]
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+80h] [rbp+7h] BYREF
  const char *v19; // [rsp+A0h] [rbp+27h]
  __int64 v20; // [rsp+A8h] [rbp+2Fh]
  PVOID *v21; // [rsp+B0h] [rbp+37h]
  __int64 v22; // [rsp+B8h] [rbp+3Fh]

  EventDescriptor = 0;
  if ( (unsigned int)*((unsigned __int16 *)P + 2) - 16 >= 0x10 )
  {
    v4 = *((unsigned __int16 *)P + 2) - 32;
    v5 = *(unsigned int *)P;
    a4 = (unsigned __int16)*((_OWORD *)P + 1) | ((unsigned __int8)BYTE2(*((_OWORD *)P + 1)) << 16);
    EventDescriptor = (EVENT_DESCRIPTOR)*((_OWORD *)P + 1);
    if ( (_DWORD)a4 == 0xFFFFFF )
    {
      if ( v4 >= (unsigned int)v5 )
      {
        v6 = (char *)P + 32;
        v7 = (char *)P + v5 + 32;
        v4 -= v5;
LABEL_12:
        UserData.Size = v5;
        v13 = (char *)P + 8;
        UserData.Reserved = 1;
        v15 = v7;
        EventDescriptor.Id = 0;
        EventDescriptor.Version = 0;
        v16 = v4;
        v17 = 0;
        v14 = 0x300000008LL;
        UserData.Ptr = (ULONGLONG)v6;
        return EtwWrite(RegHandle, &EventDescriptor, 0, 3u, &UserData);
      }
    }
    else
    {
      if ( (_DWORD)v5 != dword_1400094A8 )
      {
        result = dword_140009050;
        if ( (unsigned int)dword_140009050 <= 5 )
          return result;
        v20 = 29;
        v19 = "Event with invalid timestamp";
        v9 = (unsigned __int8 *)byte_1400073ED;
        LODWORD(v10) = *(_DWORD *)P;
        v22 = 4;
        goto LABEL_15;
      }
      if ( (unsigned __int64)(unsigned int)(a4 + 4) <= *((_QWORD *)&MaxDataSize + 1) )
      {
        v6 = (char *)(a4 + *(_QWORD *)&MaxDataSize);
        v5 = *(unsigned __int16 *)(a4 + *(_QWORD *)&MaxDataSize);
        if ( (unsigned int)v5 >= 4 && (unsigned __int64)(a4 + v5) <= *((_QWORD *)&MaxDataSize + 1) )
        {
          v7 = (char *)P + 32;
          goto LABEL_12;
        }
      }
    }
  }
  result = dword_140009050;
  if ( (unsigned int)dword_140009050 <= 5 )
    return result;
  v20 = 14;
  v19 = "Invalid event";
  v9 = (unsigned __int8 *)&word_14000729A;
  v10 = P;
  v22 = 8;
LABEL_15:
  v21 = &v10;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140009050, v9, (__int64)P, a4, 4u, &v18);
}

```

## disassembly

```asm
0x140012e9c  mov     [rsp-8+arg_0], rbx
0x140012ea1  push    rbp
0x140012ea2  lea     rbp, [rsp-57h]
0x140012ea7  sub     rsp, 0D0h
0x140012eae  mov     rax, cs:__security_cookie
0x140012eb5  xor     rax, rsp
0x140012eb8  mov     [rbp+57h+var_10], rax
0x140012ebc  mov     r8, cs:P; int
0x140012ec3  xorps   xmm0, xmm0
0x140012ec6  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x140012eca  movzx   edx, word ptr [r8+4]
0x140012ecf  add     edx, 0FFFFFFF0h
0x140012ed2  cmp     edx, 10h
0x140012ed5  jb      loc_140012FF9
0x140012edb  movups  xmm0, xmmword ptr [r8+10h]
0x140012ee0  add     edx, 0FFFFFFF0h
0x140012ee3  lea     rbx, [r8+20h]
0x140012ee7  movq    rcx, xmm0
0x140012eec  mov     rax, rcx
0x140012eef  shr     rax, 10h
0x140012ef3  movzx   r9d, al
0x140012ef7  shl     r9d, 10h
0x140012efb  movzx   eax, cx
0x140012efe  mov     ecx, [r8]
0x140012f01  or      r9d, eax
0x140012f04  movups  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x140012f08  cmp     r9d, 0FFFFFFh
0x140012f0f  jnz     short loc_140012F24
0x140012f11  cmp     edx, ecx
0x140012f13  jb      loc_140012FF9
0x140012f19  mov     r10, rbx
0x140012f1c  lea     r9, [rbx+rcx]
0x140012f20  sub     edx, ecx
0x140012f22  jmp     short loc_140012F9B
0x140012f24  cmp     ecx, cs:dword_1400094A8
0x140012f2a  jz      short loc_140012F6C
0x140012f2c  mov     eax, cs:dword_140009050
0x140012f32  cmp     eax, 5
0x140012f35  jbe     loc_14001304F
0x140012f3b  lea     rax, aEventWithInval; "Event with invalid timestamp"
0x140012f42  mov     [rbp+57h+var_28], 1Dh
0x140012f4a  mov     [rbp+57h+var_30], rax
0x140012f4e  lea     rdx, byte_1400073ED
0x140012f55  mov     eax, [r8]
0x140012f58  mov     dword ptr [rbp+57h+var_A0], eax
0x140012f5b  lea     rax, [rbp+57h+var_A0]
0x140012f5f  mov     [rbp+57h+var_18], 4
0x140012f67  jmp     loc_14001302E
0x140012f6c  mov     r11, qword ptr cs:MaxDataSize+8
0x140012f73  lea     ecx, [r9+4]
0x140012f77  cmp     rcx, r11
0x140012f7a  ja      short loc_140012FF9
0x140012f7c  mov     r10, qword ptr cs:MaxDataSize
0x140012f83  add     r10, r9
0x140012f86  movzx   ecx, word ptr [r10]
0x140012f8a  cmp     ecx, 4
0x140012f8d  jb      short loc_140012FF9
0x140012f8f  lea     rax, [r9+rcx]
0x140012f93  cmp     rax, r11
0x140012f96  ja      short loc_140012FF9
0x140012f98  mov     r9, rbx
0x140012f9b  lea     rax, [r8+8]
0x140012f9f  mov     [rbp+57h+var_88.Size], ecx
0x140012fa2  xor     ecx, ecx
0x140012fa4  mov     [rbp+57h+var_78], rax
0x140012fa8  mov     dword ptr [rbp+57h+var_88.0Ch], ecx
0x140012fab  lea     rax, [rbp+57h+var_88]
0x140012faf  mov     [rbp+57h+var_68], r9
0x140012fb3  xor     r8d, r8d; ActivityId
0x140012fb6  mov     [rbp+57h+EventDescriptor.Id], cx
0x140012fba  lea     r9d, [rcx+3]; UserDataCount
0x140012fbe  mov     [rbp+57h+EventDescriptor.Version], cl
0x140012fc1  mov     [rbp+57h+var_60], edx
0x140012fc4  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140012fc8  mov     [rbp+57h+var_5C], ecx
0x140012fcb  mov     rcx, cs:RegHandle; RegHandle
0x140012fd2  mov     [rbp+57h+var_70], 8
0x140012fda  mov     [rbp+57h+var_88.Ptr], r10
0x140012fde  mov     byte ptr [rbp+57h+var_88.0Ch], 1
0x140012fe2  mov     byte ptr [rbp+57h+var_70+4], 3
0x140012fe6  mov     [rsp+0D0h+UserData], rax; UserData
0x140012feb  call    cs:__imp_EtwWrite
0x140012ff2  nop     dword ptr [rax+rax+00h]
0x140012ff7  jmp     short loc_14001304F
0x140012ff9  mov     eax, cs:dword_140009050
0x140012fff  cmp     eax, 5
0x140013002  jbe     short loc_14001304F
0x140013004  lea     rax, aInvalidEvent; "Invalid event"
0x14001300b  mov     [rbp+57h+var_28], 0Eh
0x140013013  mov     [rbp+57h+var_30], rax
0x140013017  lea     rdx, word_14000729A; int
0x14001301e  lea     rax, [rbp+57h+var_A0]
0x140013022  mov     [rbp+57h+var_A0], r8
0x140013026  mov     [rbp+57h+var_18], 8
0x14001302e  mov     [rbp+57h+var_20], rax
0x140013032  lea     rcx, dword_140009050; int
0x140013039  lea     rax, [rbp+57h+var_50]
0x14001303d  mov     [rsp+0D0h+var_A8], rax; __int64
0x140013042  mov     dword ptr [rsp+0D0h+UserData], 4; ULONG
0x14001304a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001304f  mov     rcx, [rbp+57h+var_10]
0x140013053  xor     rcx, rsp; StackCookie
0x140013056  call    __security_check_cookie
0x14001305b  mov     rbx, [rsp+0D0h+arg_0]
0x140013063  add     rsp, 0D0h
0x14001306a  pop     rbp
0x14001306b  retn
```
