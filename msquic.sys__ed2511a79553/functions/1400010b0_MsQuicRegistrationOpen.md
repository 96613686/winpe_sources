# MsQuicRegistrationOpen

- ea: `0x1400010b0`
- end: `0x1400013bb`
- name: `MsQuicRegistrationOpen`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140001008`

## callees

- `0x1400010b0`
- `0x1400013c4`
- `0x140028a3c`
- `0x140029624`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003ead8`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400012c6`
- `ntoskrnl!_snprintf_s` at `0x1400012c6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400012ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400012ee`
- `ntoskrnl!ExInitializePushLock` at `0x1400011d3`
- `ntoskrnl!ExInitializePushLock` at `0x1400011d3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400011ee`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400011ee`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001303`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001303`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000133b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000133b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001361`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001361`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001347`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001347`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140001217`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140001217`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x14000128f`
- `ntoskrnl!MmIsDriverVerifyingByAddress` at `0x14000128f`
- `ntoskrnl!ExAllocatePool2` at `0x140001164`
- `ntoskrnl!ExAllocatePool2` at `0x140001164`

## pseudocode

```c
__int64 __fastcall MsQuicRegistrationOpen(__int64 a1, char **a2)
{
  __int64 v3; // r14
  char v4; // r15
  unsigned __int64 v5; // rsi
  int v6; // edi
  char *Pool2; // rax
  __int64 v8; // rdx
  char *v9; // rbx
  int v10; // eax
  __int64 v11; // rcx
  _QWORD *v12; // rax
  char DstBuf[128]; // [rsp+40h] [rbp-B8h] BYREF

  v3 = a1;
  if ( a1 && *(_DWORD *)(a1 + 8) == 255 )
  {
    v4 = 0;
  }
  else
  {
    v4 = 1;
    if ( !a1 )
    {
LABEL_9:
      v5 = 0;
      goto LABEL_10;
    }
  }
  if ( !*(_QWORD *)a1 )
    goto LABEL_9;
  v5 = -1;
  do
    ++v5;
  while ( *(_BYTE *)(*(_QWORD *)a1 + v5) );
LABEL_10:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, (__int64)a2, 2);
  if ( a2 && v5 < 0xFF )
  {
    LOBYTE(a1) = v4;
    v6 = QuicLibraryLazyInitialize(a1);
    if ( v6 >= 0 )
    {
      Pool2 = (char *)ExAllocatePool2(66, v5 + 153, 892429137);
      v9 = Pool2;
      if ( Pool2 )
      {
        memset(Pool2, 0, v5 + 153);
        *(_DWORD *)v9 = 0;
        if ( v3 )
          v10 = *(_DWORD *)(v3 + 8);
        else
          v10 = 0;
        *((_DWORD *)v9 + 5) = v10;
        v9[16] = v9[16] & 0xFD | (v10 != 2 ? 0 : 2);
        ExInitializePushLock((PULONG_PTR)v9 + 7);
        *((_QWORD *)v9 + 9) = v9 + 64;
        *((_QWORD *)v9 + 8) = v9 + 64;
        KeInitializeSpinLock((PKSPIN_LOCK)v9 + 10);
        *((_QWORD *)v9 + 13) = v9 + 96;
        *((_QWORD *)v9 + 12) = v9 + 96;
        *((_QWORD *)v9 + 15) = v9 + 112;
        *((_QWORD *)v9 + 14) = v9 + 112;
        ExInitializeRundownProtection((PEX_RUNDOWN_REF)v9 + 16);
        v9[144] = v5 + 1;
        if ( v5 )
          memmove(v9 + 145, *(const void **)v3, v5 + 1);
        v6 = QuicWorkerPoolInitialize(v9, *((unsigned int *)v9 + 5), v9 + 48);
        if ( v6 < 0 )
        {
          ExFreePoolWithTag(v9, 0x35316351u);
        }
        else
        {
          if ( (Microsoft_QuicEnableBits & 0x20) != 0 )
            McTemplateU0psq_EtwWriteTransfer(
              a1,
              (unsigned int)QuicRegistrationCreatedV2,
              (_DWORD)v9,
              (_DWORD)v9 + 145,
              *((_DWORD *)v9 + 5));
          if ( (MsQuicLib & 0x20) != 0 && MmIsDriverVerifyingByAddress(a2) )
          {
            v9[16] |= 1u;
            if ( (byte_14005C48E & 0x40) != 0 )
            {
              _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[ reg][%p] Verifing enabled!", v9);
              McTemplateU0s_EtwWriteTransfer(v11, (const EVENT_DESCRIPTOR *)QuicLogInfo, DstBuf);
            }
          }
          else
          {
            v9[16] &= ~1u;
          }
          if ( v4 )
          {
            KeEnterCriticalRegion();
            ExAcquirePushLockExclusiveEx(&PushLock, 0);
            v12 = (_QWORD *)qword_14005C5A0;
            *((_QWORD *)v9 + 5) = qword_14005C5A0;
            *((_QWORD *)v9 + 4) = &qword_14005C598;
            *v12 = v9 + 32;
            qword_14005C5A0 = (__int64)(v9 + 32);
            ExReleasePushLockExclusiveEx(&PushLock, 0);
            KeLeaveCriticalRegion();
          }
          *a2 = v9;
        }
      }
      else
      {
        if ( (Microsoft_QuicEnableBits & 2) != 0 )
          McTemplateU0sx_EtwWriteTransfer(a1, v8, "registration", v5 + 153);
        v6 = -1073741801;
      }
    }
  }
  else
  {
    v6 = -1073741811;
  }
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)QuicApiExitStatus, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400010b0  mov     [rsp+arg_10], rbx
0x1400010b5  mov     [rsp+arg_18], rbp
0x1400010ba  push    rsi
0x1400010bb  push    rdi
0x1400010bc  push    r12
0x1400010be  push    r14
0x1400010c0  push    r15
0x1400010c2  sub     rsp, 0D0h
0x1400010c9  mov     rax, cs:__security_cookie
0x1400010d0  xor     rax, rsp
0x1400010d3  mov     [rsp+0F8h+var_38], rax
0x1400010db  mov     r12, rdx
0x1400010de  mov     r14, rcx
0x1400010e1  mov     ebx, 0FFh
0x1400010e6  test    rcx, rcx
0x1400010e9  jz      short loc_1400010F5
0x1400010eb  cmp     [rcx+8], ebx
0x1400010ee  jnz     short loc_1400010F5
0x1400010f0  xor     r15b, r15b
0x1400010f3  jmp     short loc_1400010FD
0x1400010f5  mov     r15b, 1
0x1400010f8  test    r14, r14
0x1400010fb  jz      short loc_140001114
0x1400010fd  mov     rax, [rcx]
0x140001100  test    rax, rax
0x140001103  jz      short loc_140001114
0x140001105  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140001109  inc     rsi
0x14000110c  cmp     byte ptr [rax+rsi], 0
0x140001110  jnz     short loc_140001109
0x140001112  jmp     short loc_140001116
0x140001114  xor     esi, esi
0x140001116  test    cs:Microsoft_QuicEnableBits, 8
0x14000111d  lea     rbp, [rsi+99h]
0x140001124  jz      short loc_140001132
0x140001126  xor     r9d, r9d
0x140001129  lea     r8d, [r9+2]
0x14000112d  call    McTemplateU0qp_EtwWriteTransfer
0x140001132  test    r12, r12
0x140001135  jz      loc_14000136F
0x14000113b  cmp     rsi, rbx
0x14000113e  jnb     loc_14000136F
0x140001144  mov     cl, r15b
0x140001147  call    QuicLibraryLazyInitialize
0x14000114c  mov     edi, eax
0x14000114e  test    eax, eax
0x140001150  js      loc_140001374
0x140001156  mov     r8d, 35316351h
0x14000115c  mov     rdx, rbp
0x14000115f  mov     ecx, 42h ; 'B'
0x140001164  call    cs:__imp_ExAllocatePool2
0x14000116b  nop     dword ptr [rax+rax+00h]
0x140001170  mov     rbx, rax
0x140001173  test    rax, rax
0x140001176  jnz     short loc_14000119A
0x140001178  test    cs:Microsoft_QuicEnableBits, 2
0x14000117f  jz      short loc_140001190
0x140001181  mov     r9, rbp
0x140001184  lea     r8, aRegistration; "registration"
0x14000118b  call    McTemplateU0sx_EtwWriteTransfer
0x140001190  mov     edi, 0C0000017h
0x140001195  jmp     loc_140001374
0x14000119a  mov     r8, rbp; Size
0x14000119d  xor     edx, edx; Val
0x14000119f  mov     rcx, rbx; void *
0x1400011a2  call    memset
0x1400011a7  and     dword ptr [rbx], 0
0x1400011aa  test    r14, r14
0x1400011ad  jnz     short loc_1400011B3
0x1400011af  xor     eax, eax
0x1400011b1  jmp     short loc_1400011B7
0x1400011b3  mov     eax, [r14+8]
0x1400011b7  cmp     eax, 2
0x1400011ba  mov     [rbx+14h], eax
0x1400011bd  mov     al, [rbx+10h]
0x1400011c0  setnz   cl
0x1400011c3  and     al, 0FDh
0x1400011c5  dec     cl
0x1400011c7  and     cl, 2
0x1400011ca  or      cl, al
0x1400011cc  mov     [rbx+10h], cl
0x1400011cf  lea     rcx, [rbx+38h]; PushLock
0x1400011d3  call    cs:__imp_ExInitializePushLock
0x1400011da  nop     dword ptr [rax+rax+00h]
0x1400011df  lea     rax, [rbx+40h]
0x1400011e3  lea     rcx, [rbx+50h]; SpinLock
0x1400011e7  mov     [rax+8], rax
0x1400011eb  mov     [rax], rax
0x1400011ee  call    cs:__imp_KeInitializeSpinLock
0x1400011f5  nop     dword ptr [rax+rax+00h]
0x1400011fa  lea     rax, [rbx+60h]
0x1400011fe  mov     [rax+8], rax
0x140001202  lea     rcx, [rbx+80h]; RunRef
0x140001209  mov     [rax], rax
0x14000120c  lea     rax, [rbx+70h]
0x140001210  mov     [rax+8], rax
0x140001214  mov     [rax], rax
0x140001217  call    cs:__imp_ExInitializeRundownProtection
0x14000121e  nop     dword ptr [rax+rax+00h]
0x140001223  lea     eax, [rsi+1]
0x140001226  mov     [rbx+90h], al
0x14000122c  test    rsi, rsi
0x14000122f  jz      short loc_140001244
0x140001231  mov     rdx, [r14]; Src
0x140001234  lea     r8, [rsi+1]; Size
0x140001238  lea     rcx, [rbx+91h]; void *
0x14000123f  call    memmove
0x140001244  mov     edx, [rbx+14h]
0x140001247  lea     r8, [rbx+30h]
0x14000124b  mov     rcx, rbx
0x14000124e  call    QuicWorkerPoolInitialize
0x140001253  mov     edi, eax
0x140001255  test    eax, eax
0x140001257  js      loc_140001359
0x14000125d  test    cs:Microsoft_QuicEnableBits, 20h
0x140001264  jz      short loc_140001283
0x140001266  mov     eax, [rbx+14h]
0x140001269  lea     r9, [rbx+91h]
0x140001270  mov     r8, rbx
0x140001273  mov     dword ptr [rsp+0F8h+var_D8], eax
0x140001277  lea     rdx, QuicRegistrationCreatedV2
0x14000127e  call    McTemplateU0psq_EtwWriteTransfer
0x140001283  test    cs:MsQuicLib, 20h
0x14000128a  jz      short loc_1400012E5
0x14000128c  mov     rcx, r12; AddressWithinSection
0x14000128f  call    cs:__imp_MmIsDriverVerifyingByAddress
0x140001296  nop     dword ptr [rax+rax+00h]
0x14000129b  test    eax, eax
0x14000129d  jz      short loc_1400012E5
0x14000129f  or      byte ptr [rbx+10h], 1
0x1400012a3  test    cs:byte_14005C48E, 40h
0x1400012aa  jz      short loc_1400012E9
0x1400012ac  lea     r9, Format; "[ reg][%p] Verifing enabled!"
0x1400012b3  mov     [rsp+0F8h+var_D8], rbx
0x1400012b8  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400012bc  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x1400012c1  mov     edx, 80h; SizeInBytes
0x1400012c6  call    cs:__imp__snprintf_s
0x1400012cd  nop     dword ptr [rax+rax+00h]
0x1400012d2  lea     r8, [rsp+0F8h+DstBuf]
0x1400012d7  lea     rdx, QuicLogInfo
0x1400012de  call    McTemplateU0s_EtwWriteTransfer
0x1400012e3  jmp     short loc_1400012E9
0x1400012e5  and     byte ptr [rbx+10h], 0FEh
0x1400012e9  test    r15b, r15b
0x1400012ec  jz      short loc_140001353
0x1400012ee  call    cs:__imp_KeEnterCriticalRegion
0x1400012f5  nop     dword ptr [rax+rax+00h]
0x1400012fa  xor     edx, edx
0x1400012fc  lea     rcx, PushLock
0x140001303  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000130a  nop     dword ptr [rax+rax+00h]
0x14000130f  mov     rax, cs:qword_14005C5A0
0x140001316  lea     rdx, [rbx+20h]
0x14000131a  mov     [rdx+8], rax
0x14000131e  lea     r8, qword_14005C598
0x140001325  mov     [rdx], r8
0x140001328  lea     rcx, PushLock
0x14000132f  mov     [rax], rdx
0x140001332  mov     cs:qword_14005C5A0, rdx
0x140001339  xor     edx, edx
0x14000133b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140001342  nop     dword ptr [rax+rax+00h]
0x140001347  call    cs:__imp_KeLeaveCriticalRegion
0x14000134e  nop     dword ptr [rax+rax+00h]
0x140001353  mov     [r12], rbx
0x140001357  jmp     short loc_140001374
0x140001359  mov     edx, 35316351h; Tag
0x14000135e  mov     rcx, rbx; P
0x140001361  call    cs:__imp_ExFreePoolWithTag
0x140001368  nop     dword ptr [rax+rax+00h]
0x14000136d  jmp     short loc_140001374
0x14000136f  mov     edi, 0C000000Dh
0x140001374  test    cs:Microsoft_QuicEnableBits, 8
0x14000137b  jz      short loc_14000138C
0x14000137d  mov     r8d, edi
0x140001380  lea     rdx, QuicApiExitStatus
0x140001387  call    McTemplateU0q_EtwWriteTransfer
0x14000138c  mov     eax, edi
0x14000138e  mov     rcx, [rsp+0F8h+var_38]
0x140001396  xor     rcx, rsp; StackCookie
0x140001399  call    __security_check_cookie
0x14000139e  lea     r11, [rsp+0F8h+var_28]
0x1400013a6  mov     rbx, [r11+40h]
0x1400013aa  mov     rbp, [r11+48h]
0x1400013ae  mov     rsp, r11
0x1400013b1  pop     r15
0x1400013b3  pop     r14
0x1400013b5  pop     r12
0x1400013b7  pop     rdi
0x1400013b8  pop     rsi
0x1400013b9  retn
```
