# FveLogEventEx

- ea: `0x1400e1690`
- end: `0x1400e18f4`
- name: `FveLogEventEx`
- size: `612`
- prototype: ``
- caller_count: `33`
- callee_count: `5`
- tags: ``

## callers

- `0x14006cea8`
- `0x14009e2c0`
- `0x14009f528`
- `0x14009fb70`
- `0x1400a6f64`
- `0x1400a7898`
- `0x1400a7e30`
- `0x1400a8cec`
- `0x1400a9084`
- `0x1400a9488`
- `0x1400a9b14`
- `0x1400aa0b8`
- `0x1400ab924`
- `0x1400adcbc`
- `0x1400ae57c`
- `0x1400af494`
- `0x1400b0a04`
- `0x1400b1678`
- `0x1400b20c4`
- `0x1400b2b64`
- `0x1400b2e64`
- `0x1400b378c`
- `0x1400b85d0`
- `0x1400b9fbc`
- `0x1400c27fc`
- `0x1400c3df0`
- `0x1400c8da0`
- `0x1400cb034`
- `0x1400ccd18`
- `0x1400e09a4`
- `0x1400e806c`
- `0x1400e8cc8`
- `0x1400e9e58`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140001114`
- `0x140022bf0`
- `0x1400e1690`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400e171d`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400e171d`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400e173d`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400e173d`
- `ntoskrnl!EtwWrite` at `0x1400e17c6`
- `ntoskrnl!EtwWrite` at `0x1400e17c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e18be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e18be`

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
    if ( (unsigned int)dword_140046040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
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
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140046040, (unsigned __int8 *)word_14003CD42, 0, 0, 6u, &v26);
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
0x1400e1690  mov     [rsp-8+arg_10], rbx
0x1400e1695  push    rbp
0x1400e1696  push    rsi
0x1400e1697  push    rdi
0x1400e1698  push    r12
0x1400e169a  push    r13
0x1400e169c  push    r14
0x1400e169e  push    r15
0x1400e16a0  lea     rbp, [rsp-27h]
0x1400e16a5  sub     rsp, 100h
0x1400e16ac  mov     rax, cs:__security_cookie
0x1400e16b3  xor     rax, rsp
0x1400e16b6  mov     [rbp+57h+var_40], rax
0x1400e16ba  xorps   xmm0, xmm0
0x1400e16bd  mov     qword ptr [rsp+130h+DosName.Length], 20000h
0x1400e16c6  mov     r15, rcx
0x1400e16c9  mov     r12b, r9b
0x1400e16cc  xor     r9d, r9d
0x1400e16cf  lea     rcx, [rsp+130h+var_100]
0x1400e16d4  mov     [rsp+130h+var_100], r9w
0x1400e16da  mov     r13b, r8b
0x1400e16dd  mov     [rsp+130h+DosName.Buffer], rcx
0x1400e16e2  mov     rbx, rdx
0x1400e16e5  mov     edi, r9d
0x1400e16e8  lea     r14d, [r9+2]
0x1400e16ec  movups  xmmword ptr [rsp+130h+var_D8.Ptr], xmm0
0x1400e16f1  movups  [rbp+57h+var_C8], xmm0
0x1400e16f5  movups  [rbp+57h+var_B8], xmm0
0x1400e16f9  test    r15, r15
0x1400e16fc  jz      loc_1400E17DC
0x1400e1702  mov     rax, [r15+40h]
0x1400e1706  mov     rsi, [rax+8]
0x1400e170a  test    rsi, rsi
0x1400e170d  jz      loc_1400E17DC
0x1400e1713  cmp     [rsi+58h], r9
0x1400e1717  jz      loc_1400E17DC
0x1400e171d  call    cs:__imp_KeAreAllApcsDisabled
0x1400e1724  nop     dword ptr [rax+rax+00h]
0x1400e1729  xor     r9d, r9d
0x1400e172c  test    al, al
0x1400e172e  jnz     short loc_1400E1766
0x1400e1730  mov     rcx, [r15+40h]
0x1400e1734  lea     rdx, [rsp+130h+DosName]; DosName
0x1400e1739  mov     rcx, [rcx+78h]; VolumeDeviceObject
0x1400e173d  call    cs:__imp_IoVolumeDeviceToDosName
0x1400e1744  nop     dword ptr [rax+rax+00h]
0x1400e1749  xor     r9d, r9d
0x1400e174c  mov     edi, eax
0x1400e174e  test    eax, eax
0x1400e1750  jns     short loc_1400E1766
0x1400e1752  lea     rcx, [rsp+130h+var_100]
0x1400e1757  mov     dword ptr [rsp+130h+DosName.Length], 20000h
0x1400e175f  mov     [rsp+130h+DosName.Buffer], rcx
0x1400e1764  jmp     short loc_1400E1771
0x1400e1766  mov     rcx, [rsp+130h+DosName.Buffer]
0x1400e176b  movzx   r14d, [rsp+130h+DosName.MaximumLength]
0x1400e1771  test    r12b, r12b
0x1400e1774  jnz     short loc_1400E177C
0x1400e1776  cmp     [rbx+0Ch], r9d
0x1400e177a  jge     short loc_1400E17DC
0x1400e177c  mov     rdx, [rbx]; EventDescriptor
0x1400e177f  lea     rax, [rbx+0Ch]
0x1400e1783  mov     [rsp+130h+var_D8.Ptr], rax
0x1400e1788  xor     r8d, r8d; ActivityId
0x1400e178b  mov     dword ptr [rbp+57h+var_C8+0Ch], r9d
0x1400e178f  mov     r9d, 3; UserDataCount
0x1400e1795  movzx   eax, r14w
0x1400e1799  mov     dword ptr [rbp+57h+var_C8+8], eax
0x1400e179c  lea     rax, [rbx+8]
0x1400e17a0  mov     qword ptr [rbp+57h+var_B8], rax
0x1400e17a4  lea     rax, [rsp+130h+var_D8]
0x1400e17a9  mov     qword ptr [rbp+57h+var_D8.Size], 4
0x1400e17b1  mov     qword ptr [rbp+57h+var_C8], rcx
0x1400e17b5  mov     qword ptr [rbp+57h+var_B8+8], 4
0x1400e17bd  mov     rcx, [rsi+58h]; RegHandle
0x1400e17c1  mov     [rsp+130h+UserData], rax; UserData
0x1400e17c6  call    cs:__imp_EtwWrite
0x1400e17cd  nop     dword ptr [rax+rax+00h]
0x1400e17d2  mov     rcx, [rsp+130h+DosName.Buffer]
0x1400e17d7  xor     r9d, r9d
0x1400e17da  mov     edi, eax
0x1400e17dc  test    rbx, rbx
0x1400e17df  jz      loc_1400E18B2
0x1400e17e5  cmp     [rbx], r9
0x1400e17e8  jz      loc_1400E18B2
0x1400e17ee  test    r13b, r13b
0x1400e17f1  jnz     short loc_1400E17FD
0x1400e17f3  cmp     [rbx+0Ch], r9d
0x1400e17f7  jge     loc_1400E18B2
0x1400e17fd  mov     eax, cs:dword_140046040
0x1400e1803  cmp     eax, 4
0x1400e1806  jbe     loc_1400E18AD
0x1400e180c  mov     rdx, 400000000000h
0x1400e1816  lea     rcx, dword_140046040
0x1400e181d  call    _tlgKeywordOn
0x1400e1822  test    al, al
0x1400e1824  jz      loc_1400E18AD
0x1400e182a  mov     rdx, [rsp+130h+DosName.Buffer]
0x1400e182f  lea     rcx, [rbp+57h+var_80]
0x1400e1833  call    _tlgCreate1Sz_wchar_t
0x1400e1838  mov     ecx, [rbx+0Ch]
0x1400e183b  lea     rax, [rsp+130h+var_E8]
0x1400e1840  mov     [rbp+57h+var_70], rax
0x1400e1844  lea     rdx, word_14003CD42
0x1400e184b  mov     rax, [rbx]
0x1400e184e  xor     r9d, r9d
0x1400e1851  mov     [rsp+130h+var_E8], ecx
0x1400e1855  xor     r8d, r8d
0x1400e1858  mov     [rbp+57h+var_68], 4
0x1400e1860  movzx   ecx, word ptr [rax]
0x1400e1863  lea     rax, [rsp+130h+var_E4]
0x1400e1868  mov     [rbp+57h+var_60], rax
0x1400e186c  mov     eax, [rbx+8]
0x1400e186f  mov     [rsp+130h+var_E0], eax
0x1400e1873  lea     rax, [rsp+130h+var_E0]
0x1400e1878  mov     [rbp+57h+var_50], rax
0x1400e187c  lea     rax, [rbp+57h+var_A0]
0x1400e1880  mov     [rsp+130h+var_E4], ecx
0x1400e1884  lea     rcx, dword_140046040
0x1400e188b  mov     [rsp+130h+var_108], rax
0x1400e1890  mov     dword ptr [rsp+130h+UserData], 6
0x1400e1898  mov     [rbp+57h+var_58], 4
0x1400e18a0  mov     [rbp+57h+var_48], 4
0x1400e18a8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e18ad  mov     rcx, [rsp+130h+DosName.Buffer]; P
0x1400e18b2  lea     rax, [rsp+130h+var_100]
0x1400e18b7  cmp     rcx, rax
0x1400e18ba  jz      short loc_1400E18CA
0x1400e18bc  xor     edx, edx; Tag
0x1400e18be  call    cs:__imp_ExFreePoolWithTag
0x1400e18c5  nop     dword ptr [rax+rax+00h]
0x1400e18ca  mov     eax, edi
0x1400e18cc  mov     rcx, [rbp+57h+var_40]
0x1400e18d0  xor     rcx, rsp; StackCookie
0x1400e18d3  call    __security_check_cookie
0x1400e18d8  mov     rbx, [rsp+130h+arg_10]
0x1400e18e0  add     rsp, 100h
0x1400e18e7  pop     r15
0x1400e18e9  pop     r14
0x1400e18eb  pop     r13
0x1400e18ed  pop     r12
0x1400e18ef  pop     rdi
0x1400e18f0  pop     rsi
0x1400e18f1  pop     rbp
0x1400e18f2  retn
```
