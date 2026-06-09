# PmIsConversionInProgress(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)

- ea: `0x14002096c`
- end: `0x140020af4`
- name: `?PmIsConversionInProgress@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _PARTITION_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400254c8`

## callees

- `0x14002096c`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020ac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020ad8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020ac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020ad8`
- `ntoskrnl!ExAllocatePool2` at `0x140020997`
- `ntoskrnl!ExAllocatePool2` at `0x1400209c6`
- `ntoskrnl!ExAllocatePool2` at `0x140020997`
- `ntoskrnl!ExAllocatePool2` at `0x1400209c6`

## pseudocode

```c
__int64 __fastcall PmIsConversionInProgress(PDEVICE_OBJECT *a1, struct _PARTITION_EXTENSION *a2)
{
  _OWORD *Pool2; // rbx
  NTSTATUS v5; // edi
  _DWORD *v6; // rsi
  int v7; // eax
  __int64 v8; // rdx
  int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  char *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // eax

  Pool2 = (_OWORD *)ExAllocatePool2(258, 48, 1112108368);
  if ( Pool2 )
  {
    v6 = (_DWORD *)ExAllocatePool2(258, 56, 1112108368);
    if ( v6 )
    {
      v7 = 28;
      *Pool2 = 0;
      Pool2[1] = 0;
      Pool2[2] = 0;
      *(_DWORD *)Pool2 = 28;
      *((_DWORD *)Pool2 + 1) = -2147483620;
      v8 = *((unsigned int *)Pool2 + 6);
      if ( (_DWORD)v8 )
      {
        v10 = (unsigned int)(v8 + *((_DWORD *)Pool2 + 5));
      }
      else
      {
        v9 = *((_DWORD *)Pool2 + 4);
        if ( v9 )
          v7 = v9 + *((_DWORD *)Pool2 + 3);
        v10 = (v7 + 7) & 0xFFFFFFF8;
      }
      if ( (unsigned int)(48 - v10) >= 0x10 )
      {
        v11 = *((_QWORD *)a2 + 23);
        v12 = *((_QWORD *)a2 + 22);
        if ( *((_DWORD *)Pool2 + 5) )
          v10 = *((unsigned int *)Pool2 + 5);
        else
          *((_DWORD *)Pool2 + 5) = v10;
        v13 = (char *)Pool2 + (v8 & 0xFFFFFFFFFFFFFFF0uLL);
        *(_QWORD *)&v13[v10] = v12;
        *(_QWORD *)&v13[v10 + 8] = v11;
        *((_DWORD *)Pool2 + 6) += 16;
      }
      v5 = PmSendDeviceControl(a1[2], 0x2D9404u, Pool2, 0x30u, v6, 0x38u, 0);
      if ( v5 >= 0 )
      {
        if ( v6[1] != -2147483620
          || (v14 = (unsigned int)v6[7], (unsigned int)v14 < 0x24)
          || (unsigned int)v14 > 0x38
          || (v14 & 3) != 0
          || (v15 = v6[8], v15 < 0x14)
          || v15 > 56 - (int)v14 )
        {
          v5 = -1073739509;
        }
        else
        {
          *(_OWORD *)((char *)a2 + 88) = *(_OWORD *)((char *)v6 + v14 + 4);
        }
      }
      ExFreePoolWithTag(v6, 0);
    }
    else
    {
      v5 = -1073741670;
    }
    ExFreePoolWithTag(Pool2, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002096c  push    rbx
0x14002096e  push    rbp
0x14002096f  push    rsi
0x140020970  push    rdi
0x140020971  push    r13
0x140020973  push    r14
0x140020975  sub     rsp, 68h
0x140020979  mov     r14, rdx
0x14002097c  mov     rdi, rcx
0x14002097f  mov     esi, 42496D50h
0x140020984  mov     edx, 30h ; '0'
0x140020989  mov     r8d, esi
0x14002098c  mov     ecx, 102h
0x140020991  mov     r13d, 8000001Ch
0x140020997  call    cs:__imp_ExAllocatePool2
0x14002099e  nop     dword ptr [rax+rax+00h]
0x1400209a3  mov     rbx, rax
0x1400209a6  test    rax, rax
0x1400209a9  jnz     short loc_1400209B5
0x1400209ab  mov     edi, 0C000009Ah
0x1400209b0  jmp     loc_140020AE4
0x1400209b5  mov     eax, 38h ; '8'
0x1400209ba  mov     ebp, eax
0x1400209bc  mov     edx, eax
0x1400209be  mov     r8d, esi
0x1400209c1  mov     ecx, 102h
0x1400209c6  call    cs:__imp_ExAllocatePool2
0x1400209cd  nop     dword ptr [rax+rax+00h]
0x1400209d2  mov     rsi, rax
0x1400209d5  test    rax, rax
0x1400209d8  jnz     short loc_1400209E4
0x1400209da  mov     edi, 0C000009Ah
0x1400209df  jmp     loc_140020AD3
0x1400209e4  xorps   xmm0, xmm0
0x1400209e7  mov     eax, 1Ch
0x1400209ec  movups  xmmword ptr [rbx], xmm0
0x1400209ef  movups  xmmword ptr [rbx+10h], xmm0
0x1400209f3  movups  xmmword ptr [rbx+20h], xmm0
0x1400209f7  mov     [rbx], eax
0x1400209f9  mov     [rbx+4], r13d
0x1400209fd  mov     edx, [rbx+18h]
0x140020a00  test    edx, edx
0x140020a02  jnz     short loc_140020A1B
0x140020a04  mov     ecx, [rbx+10h]
0x140020a07  test    ecx, ecx
0x140020a09  jz      short loc_140020A10
0x140020a0b  mov     eax, [rbx+0Ch]
0x140020a0e  add     eax, ecx
0x140020a10  mov     ecx, eax
0x140020a12  add     rcx, 7
0x140020a16  and     ecx, 0FFFFFFF8h
0x140020a19  jmp     short loc_140020A20
0x140020a1b  mov     ecx, [rbx+14h]
0x140020a1e  add     ecx, edx
0x140020a20  mov     eax, 30h ; '0'
0x140020a25  sub     eax, ecx
0x140020a27  cmp     eax, 10h
0x140020a2a  jb      short loc_140020A60
0x140020a2c  mov     eax, [rbx+14h]
0x140020a2f  mov     r8, [r14+0B8h]
0x140020a36  mov     r9, [r14+0B0h]
0x140020a3d  test    eax, eax
0x140020a3f  jnz     short loc_140020A46
0x140020a41  mov     [rbx+14h], ecx
0x140020a44  jmp     short loc_140020A49
0x140020a46  mov     rcx, rax
0x140020a49  mov     rax, rdx
0x140020a4c  and     rax, 0FFFFFFFFFFFFFFF0h
0x140020a50  add     rax, rbx
0x140020a53  mov     [rcx+rax], r9
0x140020a57  mov     [rcx+rax+8], r8
0x140020a5c  add     dword ptr [rbx+18h], 10h
0x140020a60  mov     rcx, [rdi+10h]; DeviceObject
0x140020a64  mov     r9d, 30h ; '0'; InputBufferLength
0x140020a6a  mov     [rsp+98h+var_68], 0; BOOLEAN
0x140020a6f  mov     r8, rbx; InputBuffer
0x140020a72  mov     [rsp+98h+var_70], ebp; ULONG
0x140020a76  mov     edx, 2D9404h; IoControlCode
0x140020a7b  mov     [rsp+98h+var_78], rsi; PVOID
0x140020a80  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140020a85  mov     edi, eax
0x140020a87  test    eax, eax
0x140020a89  js      short loc_140020AC2
0x140020a8b  cmp     r13d, [rsi+4]
0x140020a8f  jnz     short loc_140020ABD
0x140020a91  mov     ecx, [rsi+1Ch]
0x140020a94  cmp     ecx, 24h ; '$'
0x140020a97  jb      short loc_140020ABD
0x140020a99  cmp     ecx, ebp
0x140020a9b  ja      short loc_140020ABD
0x140020a9d  test    cl, 3
0x140020aa0  jnz     short loc_140020ABD
0x140020aa2  mov     eax, [rsi+20h]
0x140020aa5  cmp     eax, 14h
0x140020aa8  jb      short loc_140020ABD
0x140020aaa  sub     ebp, ecx
0x140020aac  cmp     eax, ebp
0x140020aae  ja      short loc_140020ABD
0x140020ab0  movups  xmm0, xmmword ptr [rcx+rsi+4]
0x140020ab5  movdqu  xmmword ptr [r14+58h], xmm0
0x140020abb  jmp     short loc_140020AC2
0x140020abd  mov     edi, 0C000090Bh
0x140020ac2  xor     edx, edx; Tag
0x140020ac4  mov     rcx, rsi; P
0x140020ac7  call    cs:__imp_ExFreePoolWithTag
0x140020ace  nop     dword ptr [rax+rax+00h]
0x140020ad3  xor     edx, edx; Tag
0x140020ad5  mov     rcx, rbx; P
0x140020ad8  call    cs:__imp_ExFreePoolWithTag
0x140020adf  nop     dword ptr [rax+rax+00h]
0x140020ae4  mov     eax, edi
0x140020ae6  add     rsp, 68h
0x140020aea  pop     r14
0x140020aec  pop     r13
0x140020aee  pop     rdi
0x140020aef  pop     rsi
0x140020af0  pop     rbp
0x140020af1  pop     rbx
0x140020af2  retn
```
