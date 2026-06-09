# EfspPostCreatePrepareAndSendFsctl

- ea: `0x1400528bc`
- end: `0x140052d20`
- name: `EfspPostCreatePrepareAndSendFsctl`
- size: `1124`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14005202c`

## callees

- `0x1400077e4`
- `0x140008090`
- `0x14000c230`
- `0x14000c380`
- `0x14000c680`
- `0x14004d720`
- `0x14004e560`
- `0x14004e610`
- `0x1400528bc`
- `0x1400566c4`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140052b92`
- `ntoskrnl!KeInitializeEvent` at `0x140052b92`
- `ntoskrnl!IofCallDriver` at `0x140052c37`
- `ntoskrnl!IofCallDriver` at `0x140052c37`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052c61`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052c61`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140052bf2`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140052bf2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052cbb`
- `ntoskrnl!ExAllocatePool2` at `0x140052aea`
- `ntoskrnl!ExAllocatePool2` at `0x140052aea`

## pseudocode

```c
__int64 __fastcall EfspPostCreatePrepareAndSendFsctl(
        struct _DEVICE_OBJECT *a1,
        struct _DEVICE_OBJECT *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        int *a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        _OWORD *a10)
{
  _DWORD *v10; // r12
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  NTSTATUS Status; // ebx
  __int64 v19; // r8
  int v20; // r14d
  int *v21; // r15
  unsigned int v22; // edx
  unsigned int v23; // r13d
  int v24; // eax
  ULONG v25; // ebx
  PVOID *v26; // rsi
  _QWORD *v27; // rbx
  _DWORD *KeyBlobBuffer; // rax
  PVOID *Pool2; // rax
  __int64 v30; // r14
  __int64 v31; // rax
  _BYTE *i; // r15
  ULONG v33; // ecx
  ULONG v34; // r9d
  struct _DEVICE_OBJECT *v35; // rbx
  PIRP v36; // rax
  IRP *v37; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  __int64 v39; // rax
  __int64 v40; // rcx
  PVOID *v41; // rax
  char v43; // [rsp+50h] [rbp-99h]
  char v44; // [rsp+51h] [rbp-98h] BYREF
  char v45; // [rsp+52h] [rbp-97h]
  _DWORD Size[3]; // [rsp+54h] [rbp-95h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-89h]
  PDEVICE_OBJECT v48; // [rsp+68h] [rbp-81h]
  int *v49; // [rsp+70h] [rbp-79h]
  PDEVICE_OBJECT DeviceObject; // [rsp+78h] [rbp-71h]
  __int64 v51; // [rsp+80h] [rbp-69h]
  struct _KEVENT Event; // [rsp+88h] [rbp-61h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-49h] BYREF
  _OWORD Src[3]; // [rsp+B0h] [rbp-39h] BYREF
  __int64 v55; // [rsp+E0h] [rbp-9h]

  v10 = 0;
  v55 = 0;
  Event.Header.WaitListHead.Blink = 0;
  v43 = 0;
  v44 = 0;
  v51 = a3;
  v12 = *(_QWORD *)(a4 + 8);
  *a9 = 0;
  v13 = *(_DWORD *)a4 & 0xFFFFFFF;
  v48 = a2;
  DeviceObject = a1;
  v14 = a7;
  v49 = (int *)a4;
  *(_QWORD *)&Size[1] = 0;
  memset(Src, 0, sizeof(Src));
  *(_OWORD *)&Event.Header.Lock = 0;
  IoStatusBlock = 0;
  v15 = v13 - 1;
  if ( !v15 )
  {
    v20 = 3;
    v21 = a6;
    *a10 = *(_OWORD *)(a7 + 16);
    *a9 = 1;
    goto LABEL_15;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v20 = 1;
    v21 = (int *)Src;
    v10 = (_DWORD *)a7;
    v24 = 0;
    goto LABEL_17;
  }
  v17 = v16 - 2;
  if ( v17 )
  {
    if ( v17 != 4 )
    {
      Status = -1073741811;
      v19 = 1673;
LABEL_59:
      EfspTraceLogAssert(v14, 1, v19);
      return (unsigned int)Status;
    }
    v20 = 0;
    v21 = (int *)Src;
    v22 = 56;
    Size[0] = 56;
    goto LABEL_7;
  }
  v21 = a6;
  *a10 = *(_OWORD *)(v12 + 16);
  *a9 = 1;
  v20 = ((*(int *)a4 >> 31) & 4) + 6;
  if ( a7 && (*(_DWORD *)(a4 + 4) & 1) == 0 )
  {
    v20 |= 1u;
LABEL_15:
    v10 = (_DWORD *)a7;
  }
  v24 = *a6;
LABEL_17:
  v22 = v24 + 56;
  Size[0] = v24 + 56;
  if ( !v10 )
  {
LABEL_7:
    v14 = v22;
    goto LABEL_8;
  }
  v14 = v22 + *v10;
  if ( (unsigned int)v14 < v22 )
  {
    v19 = 1700;
    goto LABEL_58;
  }
LABEL_8:
  v23 = (v14 + 15) & 0xFFFFFFF0;
  if ( v23 < (unsigned int)v14 )
  {
    v19 = 1706;
LABEL_58:
    Status = -1073741675;
    goto LABEL_59;
  }
  v25 = v23 + 32;
  v47 = v23 + 32;
  if ( v23 + 32 < v23 )
  {
    v19 = 1716;
    goto LABEL_58;
  }
  v45 = 0;
  if ( a2 )
  {
    if ( (a5 & 1) == 0 )
    {
      EfspCanOffloadCrypto(v14, (unsigned int)v21[1], a8, &v44);
      v43 = v44;
      if ( v44 == 1 )
      {
        if ( (unsigned __int8)EfspIsCryptoOffloadTurnedOffByOverride() == 1 )
        {
          v43 = 0;
        }
        else
        {
          v26 = 0;
          *(_QWORD *)&Size[1] = AllocateAndSetContextDataBlock(0);
          v27 = *(_QWORD **)&Size[1];
          if ( !*(_QWORD *)&Size[1] )
            goto LABEL_27;
          KeyBlobBuffer = GetKeyBlobBufferEx(v21[1], v21[2]);
          *v27 = KeyBlobBuffer;
          if ( !KeyBlobBuffer )
            goto LABEL_27;
          Status = EfspDevCryptoSetup(v48);
          if ( Status < 0 )
            goto LABEL_46;
          v45 = 1;
          v25 = v23 + 32;
        }
      }
    }
  }
  Pool2 = (PVOID *)ExAllocatePool2(256, v25, 1836279365);
  v26 = Pool2;
  if ( !Pool2 )
  {
LABEL_27:
    Status = -1073741670;
    goto LABEL_46;
  }
  memset(Pool2, 0, v25);
  *(_DWORD *)v26 = v20;
  *((_DWORD *)v26 + 4) = v20;
  *((_DWORD *)v26 + 6) = v20;
  v30 = Size[0];
  *((_BYTE *)v26 + 6) = v43;
  v26[1] = *(PVOID *)&Size[1];
  *((_WORD *)v26 + 2) = 21327;
  *(_QWORD *)&Size[1] = 0;
  *((_DWORD *)v26 + 5) = 1;
  *((_DWORD *)v26 + 7) = v23;
  memmove(v26 + 4, v21, (unsigned int)v30);
  if ( v10 )
    memmove((char *)v26 + v30 + 32, v10, (unsigned int)*v10);
  if ( v21 != (int *)Src )
  {
    v31 = (unsigned int)*v21;
    for ( i = v21 + 14; v31; --v31 )
      *i++ = 0;
  }
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  if ( *v49 >= 0 )
  {
    v33 = 590043;
  }
  else
  {
    v33 = 590039;
    *(_DWORD *)v26 = 3;
    *((_DWORD *)v26 + 4) = 3;
  }
  v34 = v25;
  v35 = DeviceObject;
  v36 = IoBuildDeviceIoControlRequest(v33, DeviceObject, v26, v34, 0, 0, 0, &Event, &IoStatusBlock);
  v37 = v36;
  if ( v36 )
  {
    CurrentStackLocation = v36->Tail.Overlay.CurrentStackLocation;
    v39 = v51;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 13;
    CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(*(_QWORD *)(v39 + 184) + 48LL);
    Status = IofCallDriver(v35, v37);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status >= 0 )
      goto LABEL_49;
    Status = -1073741790;
LABEL_46:
    if ( *(_QWORD *)&Size[1] )
      FreeContextDataBlock((PVOID *)&Size[1]);
    if ( !v26 )
      goto LABEL_54;
    goto LABEL_49;
  }
  Status = -1073741670;
LABEL_49:
  if ( v26[1] )
    FreeContextDataBlock(v26 + 1);
  v40 = v47;
  v41 = v26;
  if ( v47 )
  {
    do
    {
      *(_BYTE *)v41 = 0;
      v41 = (PVOID *)((char *)v41 + 1);
      --v40;
    }
    while ( v40 );
  }
  ExFreePoolWithTag(v26, 0);
LABEL_54:
  if ( Status < 0 && v45 == 1 )
    EfspDevCryptoSetup(v48);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400528bc  mov     [rsp-8+arg_10], rbx
0x1400528c1  push    rbp
0x1400528c2  push    rsi
0x1400528c3  push    rdi
0x1400528c4  push    r12
0x1400528c6  push    r13
0x1400528c8  push    r14
0x1400528ca  push    r15
0x1400528cc  lea     rbp, [rsp-7]
0x1400528d1  sub     rsp, 0F0h
0x1400528d8  mov     rax, cs:__security_cookie
0x1400528df  xor     rax, rsp
0x1400528e2  mov     [rbp+37h+var_38], rax
0x1400528e6  mov     r10, [rbp+37h+arg_40]
0x1400528ed  xor     eax, eax
0x1400528ef  mov     r11, [rbp+37h+arg_48]
0x1400528f6  xorps   xmm0, xmm0
0x1400528f9  xor     r12d, r12d
0x1400528fc  mov     [rbp+37h+var_40], rax
0x140052900  mov     [rbp+37h+Event.Header.WaitListHead.Blink], rax
0x140052904  mov     rsi, rdx
0x140052907  mov     [rsp+120h+var_D0], al
0x14005290b  mov     [rsp+120h+var_CF], al
0x14005290f  mov     [rbp+37h+var_A0], r8
0x140052913  lea     edi, [r12+1]
0x140052918  mov     r8, [r9+8]
0x14005291c  mov     [r10], r12d
0x14005291f  mov     eax, [r9]
0x140052922  and     eax, 0FFFFFFFh
0x140052927  mov     [rsp+120h+var_B8], rdx
0x14005292c  mov     rdx, [rbp+37h+arg_28]
0x140052930  mov     [rbp+37h+DeviceObject], rcx
0x140052934  mov     rcx, [rbp+37h+arg_30]
0x140052938  mov     [rbp+37h+var_B0], r9
0x14005293c  mov     qword ptr [rsp+120h+Size+4], r12
0x140052941  movups  [rbp+37h+Src], xmm0
0x140052945  movups  [rbp+37h+var_60], xmm0
0x140052949  movups  [rbp+37h+var_50], xmm0
0x14005294d  movups  xmmword ptr [rbp+37h+Event.Header], xmm0
0x140052951  movups  xmmword ptr [rbp+37h+var_80], xmm0
0x140052955  sub     eax, edi
0x140052957  jz      loc_1400529ED
0x14005295d  sub     eax, edi
0x14005295f  jz      short loc_1400529DF
0x140052961  sub     eax, 2
0x140052964  jz      short loc_1400529AD
0x140052966  cmp     eax, 4
0x140052969  jz      short loc_140052980
0x14005296b  mov     ebx, 0C000000Dh
0x140052970  mov     edx, edi
0x140052972  mov     r9d, ebx
0x140052975  mov     r8d, 689h
0x14005297b  jmp     loc_140052CF1
0x140052980  xor     r14d, r14d
0x140052983  lea     r15, [rbp+37h+Src]
0x140052987  lea     edx, [r14+38h]
0x14005298b  mov     dword ptr [rsp+120h+Size], edx
0x14005298f  mov     ecx, edx
0x140052991  lea     r13d, [rcx+0Fh]
0x140052995  and     r13d, 0FFFFFFF0h
0x140052999  cmp     r13d, ecx
0x14005299c  jnb     loc_140052A30
0x1400529a2  mov     r8d, 6AAh
0x1400529a8  jmp     loc_140052CE6
0x1400529ad  movups  xmm0, xmmword ptr [r8+10h]
0x1400529b2  mov     r15, rdx
0x1400529b5  movdqu  xmmword ptr [r11], xmm0
0x1400529ba  mov     [r10], edi
0x1400529bd  mov     r14d, [r9]
0x1400529c0  sar     r14d, 1Fh
0x1400529c4  and     r14d, 4
0x1400529c8  add     r14d, 6
0x1400529cc  test    rcx, rcx
0x1400529cf  jz      short loc_140052A05
0x1400529d1  mov     eax, [r9+4]
0x1400529d5  test    dil, al
0x1400529d8  jnz     short loc_140052A05
0x1400529da  or      r14d, edi
0x1400529dd  jmp     short loc_140052A02
0x1400529df  mov     r14d, edi
0x1400529e2  lea     r15, [rbp+37h+Src]
0x1400529e6  mov     r12, rcx
0x1400529e9  xor     eax, eax
0x1400529eb  jmp     short loc_140052A07
0x1400529ed  movups  xmm0, xmmword ptr [rcx+10h]
0x1400529f1  mov     r14d, 3
0x1400529f7  mov     r15, rdx
0x1400529fa  movdqu  xmmword ptr [r11], xmm0
0x1400529ff  mov     [r10], edi
0x140052a02  mov     r12, rcx
0x140052a05  mov     eax, [rdx]
0x140052a07  lea     edx, [rax+38h]
0x140052a0a  mov     dword ptr [rsp+120h+Size], edx
0x140052a0e  test    r12, r12
0x140052a11  jz      loc_14005298F
0x140052a17  mov     ecx, [r12]
0x140052a1b  add     ecx, edx
0x140052a1d  cmp     ecx, edx
0x140052a1f  jnb     loc_140052991
0x140052a25  mov     r8d, 6A4h
0x140052a2b  jmp     loc_140052CE6
0x140052a30  lea     ebx, [r13+20h]
0x140052a34  mov     [rsp+120h+var_C0], ebx
0x140052a38  cmp     ebx, r13d
0x140052a3b  jb      loc_140052CE0
0x140052a41  mov     [rsp+120h+var_CE], 0
0x140052a46  test    rsi, rsi
0x140052a49  jz      loc_140052ADD
0x140052a4f  test    [rbp+37h+arg_20], dil
0x140052a53  jnz     loc_140052ADD
0x140052a59  mov     r8, [rbp+37h+arg_38]
0x140052a5d  lea     r9, [rsp+120h+var_CF]
0x140052a62  mov     edx, [r15+4]
0x140052a66  call    EfspCanOffloadCrypto
0x140052a6b  mov     al, [rsp+120h+var_CF]
0x140052a6f  mov     [rsp+120h+var_D0], al
0x140052a73  cmp     al, dil
0x140052a76  jnz     short loc_140052ADD
0x140052a78  call    EfspIsCryptoOffloadTurnedOffByOverride
0x140052a7d  cmp     al, dil
0x140052a80  jnz     short loc_140052A89
0x140052a82  mov     [rsp+120h+var_D0], 0
0x140052a87  jmp     short loc_140052ADD
0x140052a89  xor     ecx, ecx
0x140052a8b  xor     esi, esi
0x140052a8d  call    AllocateAndSetContextDataBlock
0x140052a92  mov     qword ptr [rsp+120h+Size+4], rax
0x140052a97  mov     rbx, rax
0x140052a9a  test    rax, rax
0x140052a9d  jnz     short loc_140052AA9
0x140052a9f  mov     ebx, 0C000009Ah
0x140052aa4  jmp     loc_140052C79
0x140052aa9  mov     edx, [r15+8]
0x140052aad  mov     ecx, [r15+4]
0x140052ab1  call    GetKeyBlobBufferEx
0x140052ab6  mov     [rbx], rax
0x140052ab9  test    rax, rax
0x140052abc  jz      short loc_140052A9F
0x140052abe  mov     rcx, [rsp+120h+var_B8]; DeviceObject
0x140052ac3  xor     edx, edx
0x140052ac5  call    EfspDevCryptoSetup
0x140052aca  mov     ebx, eax
0x140052acc  test    eax, eax
0x140052ace  js      loc_140052C79
0x140052ad4  mov     [rsp+120h+var_CE], dil
0x140052ad9  lea     ebx, [r13+20h]
0x140052add  mov     edx, ebx
0x140052adf  mov     ecx, 100h
0x140052ae4  mov     r8d, 6D736645h
0x140052aea  call    cs:__imp_ExAllocatePool2
0x140052af1  nop     dword ptr [rax+rax+00h]
0x140052af6  mov     rsi, rax
0x140052af9  test    rax, rax
0x140052afc  jz      short loc_140052A9F
0x140052afe  mov     r8d, ebx; Size
0x140052b01  xor     edx, edx; Val
0x140052b03  mov     rcx, rax; void *
0x140052b06  call    memset
0x140052b0b  mov     al, [rsp+120h+var_D0]
0x140052b0f  lea     rcx, [rsi+20h]; void *
0x140052b13  mov     [rsi], r14d
0x140052b16  mov     rdx, r15; Src
0x140052b19  mov     [rsi+10h], r14d
0x140052b1d  mov     [rsi+18h], r14d
0x140052b21  mov     r14d, dword ptr [rsp+120h+Size]
0x140052b26  mov     [rsi+6], al
0x140052b29  mov     r8d, r14d; Size
0x140052b2c  mov     rax, qword ptr [rsp+120h+Size+4]
0x140052b31  mov     [rsi+8], rax
0x140052b35  mov     word ptr [rsi+4], 534Fh
0x140052b3b  mov     qword ptr [rsp+120h+Size+4], 0
0x140052b44  mov     [rsi+14h], edi
0x140052b47  mov     [rsi+1Ch], r13d
0x140052b4b  call    memmove
0x140052b50  test    r12, r12
0x140052b53  jz      short loc_140052B68
0x140052b55  mov     r8d, [r12]; Size
0x140052b59  lea     rcx, [r14+20h]
0x140052b5d  add     rcx, rsi; void *
0x140052b60  mov     rdx, r12; Src
0x140052b63  call    memmove
0x140052b68  lea     rax, [rbp+37h+Src]
0x140052b6c  cmp     r15, rax
0x140052b6f  jz      short loc_140052B89
0x140052b71  mov     eax, [r15]
0x140052b74  add     r15, 38h ; '8'
0x140052b78  test    rax, rax
0x140052b7b  jz      short loc_140052B89
0x140052b7d  mov     byte ptr [r15], 0
0x140052b81  add     r15, rdi
0x140052b84  sub     rax, rdi
0x140052b87  jnz     short loc_140052B7D
0x140052b89  xor     r8d, r8d; State
0x140052b8c  lea     rcx, [rbp+37h+Event]; Event
0x140052b90  mov     edx, edi; Type
0x140052b92  call    cs:__imp_KeInitializeEvent
0x140052b99  nop     dword ptr [rax+rax+00h]
0x140052b9e  mov     rax, [rbp+37h+var_B0]
0x140052ba2  cmp     dword ptr [rax], 0
0x140052ba5  jge     short loc_140052BB8
0x140052ba7  mov     eax, 3
0x140052bac  mov     ecx, 900D7h
0x140052bb1  mov     [rsi], eax
0x140052bb3  mov     [rsi+10h], eax
0x140052bb6  jmp     short loc_140052BBD
0x140052bb8  mov     ecx, 900DBh; IoControlCode
0x140052bbd  lea     rax, [rbp+37h+var_80]
0x140052bc1  mov     r9d, ebx; InputBufferLength
0x140052bc4  mov     rbx, [rbp+37h+DeviceObject]
0x140052bc8  mov     r8, rsi; InputBuffer
0x140052bcb  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x140052bd0  mov     rdx, rbx; DeviceObject
0x140052bd3  lea     rax, [rbp+37h+Event]
0x140052bd7  mov     [rsp+120h+var_E8], rax; Event
0x140052bdc  mov     [rsp+120h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140052be1  mov     [rsp+120h+OutputBufferLength], 0; OutputBufferLength
0x140052be9  mov     [rsp+120h+OutputBuffer], 0; OutputBuffer
0x140052bf2  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140052bf9  nop     dword ptr [rax+rax+00h]
0x140052bfe  mov     rcx, rax
0x140052c01  test    rax, rax
0x140052c04  jnz     short loc_140052C10
0x140052c06  mov     ebx, 0C000009Ah
0x140052c0b  jmp     loc_140052C90
0x140052c10  mov     r8, [rax+0B8h]
0x140052c17  mov     rax, [rbp+37h+var_A0]
0x140052c1b  mov     word ptr [r8-48h], 0Dh
0x140052c22  mov     rax, [rax+0B8h]
0x140052c29  mov     rdx, [rax+30h]
0x140052c2d  mov     [r8-18h], rdx
0x140052c31  mov     rdx, rcx; Irp
0x140052c34  mov     rcx, rbx; DeviceObject
0x140052c37  call    cs:__imp_IofCallDriver
0x140052c3e  nop     dword ptr [rax+rax+00h]
0x140052c43  mov     ebx, eax
0x140052c45  cmp     eax, 103h
0x140052c4a  jnz     short loc_140052C70
0x140052c4c  xor     r9d, r9d; Alertable
0x140052c4f  mov     [rsp+120h+OutputBuffer], 0; Timeout
0x140052c58  xor     r8d, r8d; WaitMode
0x140052c5b  lea     rcx, [rbp+37h+Event]; Object
0x140052c5f  xor     edx, edx; WaitReason
0x140052c61  call    cs:__imp_KeWaitForSingleObject
0x140052c68  nop     dword ptr [rax+rax+00h]
0x140052c6d  mov     ebx, dword ptr [rbp+37h+var_80]
0x140052c70  test    ebx, ebx
0x140052c72  jns     short loc_140052C90
0x140052c74  mov     ebx, 0C0000022h
0x140052c79  cmp     qword ptr [rsp+120h+Size+4], 0
0x140052c7f  jz      short loc_140052C8B
0x140052c81  lea     rcx, [rsp+120h+Size+4]
0x140052c86  call    FreeContextDataBlock
0x140052c8b  test    rsi, rsi
0x140052c8e  jz      short loc_140052CC7
0x140052c90  lea     rcx, [rsi+8]
0x140052c94  cmp     qword ptr [rcx], 0
0x140052c98  jz      short loc_140052C9F
0x140052c9a  call    FreeContextDataBlock
0x140052c9f  mov     ecx, [rsp+120h+var_C0]
0x140052ca3  mov     rax, rsi
0x140052ca6  test    rcx, rcx
0x140052ca9  jz      short loc_140052CB6
0x140052cab  mov     byte ptr [rax], 0
0x140052cae  add     rax, rdi
0x140052cb1  sub     rcx, rdi
0x140052cb4  jnz     short loc_140052CAB
0x140052cb6  xor     edx, edx; Tag
0x140052cb8  mov     rcx, rsi; P
0x140052cbb  call    cs:__imp_ExFreePoolWithTag
0x140052cc2  nop     dword ptr [rax+rax+00h]
0x140052cc7  test    ebx, ebx
0x140052cc9  jns     short loc_140052CF6
0x140052ccb  cmp     [rsp+120h+var_CE], dil
0x140052cd0  jnz     short loc_140052CF6
0x140052cd2  mov     rcx, [rsp+120h+var_B8]; DeviceObject
0x140052cd7  mov     edx, edi
0x140052cd9  call    EfspDevCryptoSetup
0x140052cde  jmp     short loc_140052CF6
0x140052ce0  mov     r8d, 6B4h
0x140052ce6  mov     r9d, 0C0000095h
0x140052cec  mov     edx, edi
0x140052cee  mov     ebx, r9d
0x140052cf1  call    EfspTraceLogAssert
0x140052cf6  mov     eax, ebx
0x140052cf8  mov     rcx, [rbp+37h+var_38]
0x140052cfc  xor     rcx, rsp; StackCookie
0x140052cff  call    __security_check_cookie
0x140052d04  mov     rbx, [rsp+120h+arg_10]
0x140052d0c  add     rsp, 0F0h
0x140052d13  pop     r15
0x140052d15  pop     r14
0x140052d17  pop     r13
0x140052d19  pop     r12
0x140052d1b  pop     rdi
0x140052d1c  pop     rsi
0x140052d1d  pop     rbp
0x140052d1e  retn
```
