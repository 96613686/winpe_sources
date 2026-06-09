# NatLogDroppedPacket

- ea: `0x14001066c`
- end: `0x1400109f2`
- name: `NatLogDroppedPacket`
- size: `902`
- prototype: `void __fastcall(__int64 **, unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140022320`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140002200`
- `0x14001066c`
- `0x14002c6d0`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x140010930`
- `ntoskrnl!IoWMIWriteEvent` at `0x140010930`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400107d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400107d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400107bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400107bb`

## pseudocode

```c
void __fastcall NatLogDroppedPacket(__int64 **a1, unsigned int a2, int a3)
{
  int v3; // edi
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  KIRQL v8; // al
  __int64 v9; // rsi
  char v10; // si
  __int64 *v11; // rax
  int v12; // ecx
  unsigned __int8 *v13; // rcx
  __int64 *v14; // rcx
  NTSTATUS v15; // eax
  _QWORD WnodeEventItem[12]; // [rsp+30h] [rbp-49h] BYREF

  v3 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, a2, a3);
  }
  if ( dword_140032228 )
  {
    if ( (*((_DWORD *)a1 + 13) & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          v7 = 36;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v8 = KeAcquireSpinLockRaiseToDpc(&NatWmiLock);
      v9 = qword_140032250;
      KeReleaseSpinLock(&NatWmiLock, v8);
      if ( v9 )
      {
        memset(WnodeEventItem, 0, 0x54u);
        LOWORD(WnodeEventItem[0]) = 84;
        WnodeEventItem[3] = PacketDroppedEventGuid;
        HIDWORD(WnodeEventItem[0]) = 0;
        HIDWORD(WnodeEventItem[5]) = 655872;
        WnodeEventItem[1] = v9;
        WnodeEventItem[2] = MEMORY[0xFFFFF78000000014];
        v10 = *((_BYTE *)a1[1] + 9);
        WnodeEventItem[6] = a1[3];
        LOBYTE(WnodeEventItem[10]) = v10;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
        }
        if ( v3 )
          LOBYTE(v3) = (a2 == 0) + 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
        }
        v11 = *a1;
        v12 = 0;
        HIDWORD(WnodeEventItem[7]) = 0;
        BYTE1(WnodeEventItem[10]) = v3;
        do
        {
          v12 += *((_DWORD *)v11 + 6);
          HIDWORD(WnodeEventItem[7]) = v12;
          v11 = (__int64 *)*v11;
        }
        while ( v11 );
        if ( v10 == 6 || v10 == 17 )
        {
          v14 = a1[5];
          LODWORD(WnodeEventItem[7]) = *(_DWORD *)v14;
          if ( v10 == 6 )
          {
            WnodeEventItem[8] = *(__int64 *)((char *)v14 + 4);
            LODWORD(WnodeEventItem[9]) = *((unsigned __int16 *)v14 + 7);
            HIDWORD(WnodeEventItem[9]) = *((_WORD *)v14 + 6) & 0x3F00;
          }
        }
        else if ( v10 == 1 )
        {
          v13 = (unsigned __int8 *)a1[5];
          LODWORD(WnodeEventItem[8]) = *v13;
          HIDWORD(WnodeEventItem[8]) = v13[1];
        }
        v15 = IoWMIWriteEvent(WnodeEventItem);
        if ( v15 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            37,
            WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids,
            (unsigned int)v15);
        }
        *((_DWORD *)a1 + 13) |= 4u;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v7 = 39;
        goto LABEL_56;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v7 = 34;
LABEL_56:
      WPP_SF_(v6->AttachedDevice, v7, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14001066c  mov     [rsp-8+arg_10], rbx
0x140010671  push    rbp
0x140010672  push    rsi
0x140010673  push    rdi
0x140010674  push    r12
0x140010676  push    r13
0x140010678  push    r14
0x14001067a  push    r15
0x14001067c  lea     rbp, [rsp-27h]
0x140010681  sub     rsp, 0A0h
0x140010688  mov     rax, cs:__security_cookie
0x14001068f  xor     rax, rsp
0x140010692  mov     [rbp+57h+var_40], rax
0x140010696  mov     edi, r8d
0x140010699  mov     r14d, edx
0x14001069c  mov     rbx, rcx
0x14001069f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106a6  lea     r15, WPP_GLOBAL_Control
0x1400106ad  lea     r13, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x1400106b4  mov     sil, 6
0x1400106b7  mov     r12b, 1
0x1400106ba  cmp     rcx, r15
0x1400106bd  jz      short loc_1400106E6
0x1400106bf  mov     eax, [rcx+2Ch]
0x1400106c2  test    r12b, al
0x1400106c5  jz      short loc_1400106E6
0x1400106c7  cmp     [rcx+29h], sil
0x1400106cb  jb      short loc_1400106E6
0x1400106cd  mov     rcx, [rcx+18h]
0x1400106d1  mov     edx, 20h ; ' '
0x1400106d6  mov     [rsp+0D0h+var_B0], r8d
0x1400106db  mov     r9d, r14d
0x1400106de  mov     r8, r13
0x1400106e1  call    WPP_SF_dd
0x1400106e6  cmp     cs:dword_140032228, 0
0x1400106ed  jnz     short loc_14001074E
0x1400106ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106f6  cmp     rcx, r15
0x1400106f9  jz      loc_1400109CA
0x1400106ff  mov     eax, [rcx+2Ch]
0x140010702  test    r12b, al
0x140010705  jz      short loc_14001071E
0x140010707  cmp     byte ptr [rcx+29h], 2
0x14001070b  jb      short loc_14001071E
0x14001070d  mov     rcx, [rcx+18h]
0x140010711  mov     edx, 21h ; '!'
0x140010716  mov     r8, r13
0x140010719  call    WPP_SF_
0x14001071e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010725  cmp     rcx, r15
0x140010728  jz      loc_1400109CA
0x14001072e  mov     eax, [rcx+2Ch]
0x140010731  test    r12b, al
0x140010734  jz      loc_1400109CA
0x14001073a  cmp     [rcx+29h], sil
0x14001073e  jb      loc_1400109CA
0x140010744  mov     edx, 22h ; '"'
0x140010749  jmp     loc_1400109BE
0x14001074e  mov     eax, [rbx+34h]
0x140010751  test    al, 4
0x140010753  jz      short loc_1400107B4
0x140010755  mov     rcx, cs:WPP_GLOBAL_Control
0x14001075c  cmp     rcx, r15
0x14001075f  jz      loc_1400109CA
0x140010765  mov     eax, [rcx+2Ch]
0x140010768  test    r12b, al
0x14001076b  jz      short loc_140010784
0x14001076d  cmp     byte ptr [rcx+29h], 2
0x140010771  jb      short loc_140010784
0x140010773  mov     rcx, [rcx+18h]
0x140010777  mov     edx, 23h ; '#'
0x14001077c  mov     r8, r13
0x14001077f  call    WPP_SF_
0x140010784  mov     rcx, cs:WPP_GLOBAL_Control
0x14001078b  cmp     rcx, r15
0x14001078e  jz      loc_1400109CA
0x140010794  mov     eax, [rcx+2Ch]
0x140010797  test    r12b, al
0x14001079a  jz      loc_1400109CA
0x1400107a0  cmp     [rcx+29h], sil
0x1400107a4  jb      loc_1400109CA
0x1400107aa  mov     edx, 24h ; '$'
0x1400107af  jmp     loc_1400109BE
0x1400107b4  lea     rcx, NatWmiLock; SpinLock
0x1400107bb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400107c2  nop     dword ptr [rax+rax+00h]
0x1400107c7  mov     rsi, cs:qword_140032250
0x1400107ce  lea     rcx, NatWmiLock; SpinLock
0x1400107d5  mov     dl, al; NewIrql
0x1400107d7  call    cs:__imp_KeReleaseSpinLock
0x1400107de  nop     dword ptr [rax+rax+00h]
0x1400107e3  test    rsi, rsi
0x1400107e6  jz      loc_140010974
0x1400107ec  mov     r15d, 54h ; 'T'
0x1400107f2  lea     rcx, [rbp+57h+WnodeEventItem]; void *
0x1400107f6  mov     r8d, r15d; Size
0x1400107f9  xor     edx, edx; Val
0x1400107fb  call    memset
0x140010800  lea     rax, PacketDroppedEventGuid
0x140010807  mov     [rbp+57h+WnodeEventItem], r15w
0x14001080c  mov     [rbp+57h+var_88], rax
0x140010810  mov     rax, 0FFFFF78000000014h
0x14001081a  mov     [rbp+57h+var_9C], 0
0x140010821  mov     [rbp+57h+var_74], 0A0200h
0x140010828  mov     [rbp+57h+var_98], rsi
0x14001082c  mov     rax, [rax]
0x14001082f  mov     [rbp+57h+var_90], rax
0x140010833  mov     rax, [rbx+8]
0x140010837  mov     sil, [rax+9]
0x14001083b  mov     eax, [rbx+18h]
0x14001083e  mov     [rbp+57h+var_70], eax
0x140010841  mov     eax, [rbx+1Ch]
0x140010844  mov     [rbp+57h+var_6C], eax
0x140010847  mov     [rbp+57h+var_50], sil
0x14001084b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010852  lea     r15, WPP_GLOBAL_Control
0x140010859  cmp     rcx, r15
0x14001085c  jz      short loc_14001087D
0x14001085e  mov     eax, [rcx+2Ch]
0x140010861  test    r12b, al
0x140010864  jz      short loc_14001087D
0x140010866  cmp     byte ptr [rcx+29h], 6
0x14001086a  jb      short loc_14001087D
0x14001086c  mov     rcx, [rcx+18h]
0x140010870  mov     edx, 41h ; 'A'
0x140010875  mov     r8, r13
0x140010878  call    WPP_SF_
0x14001087d  test    edi, edi
0x14001087f  jz      short loc_14001088B
0x140010881  test    r14d, r14d
0x140010884  setz    dil
0x140010888  add     dil, r12b
0x14001088b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010892  cmp     rcx, r15
0x140010895  jz      short loc_1400108B6
0x140010897  mov     eax, [rcx+2Ch]
0x14001089a  test    r12b, al
0x14001089d  jz      short loc_1400108B6
0x14001089f  cmp     byte ptr [rcx+29h], 6
0x1400108a3  jb      short loc_1400108B6
0x1400108a5  mov     rcx, [rcx+18h]
0x1400108a9  mov     edx, 42h ; 'B'
0x1400108ae  mov     r8, r13
0x1400108b1  call    WPP_SF_
0x1400108b6  mov     rax, [rbx]
0x1400108b9  xor     ecx, ecx
0x1400108bb  mov     [rbp+57h+var_64], ecx
0x1400108be  mov     [rbp+57h+var_4F], dil
0x1400108c2  add     ecx, [rax+18h]
0x1400108c5  mov     [rbp+57h+var_64], ecx
0x1400108c8  mov     rax, [rax]
0x1400108cb  test    rax, rax
0x1400108ce  jnz     short loc_1400108C2
0x1400108d0  cmp     sil, 6
0x1400108d4  jz      short loc_1400108F4
0x1400108d6  cmp     sil, 11h
0x1400108da  jz      short loc_1400108F4
0x1400108dc  cmp     sil, r12b
0x1400108df  jnz     short loc_14001092C
0x1400108e1  mov     rcx, [rbx+28h]
0x1400108e5  movzx   eax, byte ptr [rcx]
0x1400108e8  mov     [rbp+57h+var_60], eax
0x1400108eb  movzx   eax, byte ptr [rcx+1]
0x1400108ef  mov     [rbp+57h+var_5C], eax
0x1400108f2  jmp     short loc_14001092C
0x1400108f4  mov     rcx, [rbx+28h]
0x1400108f8  movzx   eax, word ptr [rcx]
0x1400108fb  mov     [rbp+57h+var_68], ax
0x1400108ff  movzx   eax, word ptr [rcx+2]
0x140010903  mov     [rbp+57h+var_66], ax
0x140010907  cmp     sil, 6
0x14001090b  jnz     short loc_14001092C
0x14001090d  mov     eax, [rcx+4]
0x140010910  mov     [rbp+57h+var_60], eax
0x140010913  mov     eax, [rcx+8]
0x140010916  mov     [rbp+57h+var_5C], eax
0x140010919  movzx   eax, word ptr [rcx+0Eh]
0x14001091d  mov     [rbp+57h+var_58], eax
0x140010920  movzx   eax, word ptr [rcx+0Ch]
0x140010924  and     eax, 3F00h
0x140010929  mov     [rbp+57h+var_54], eax
0x14001092c  lea     rcx, [rbp+57h+WnodeEventItem]; WnodeEventItem
0x140010930  call    cs:__imp_IoWMIWriteEvent
0x140010937  nop     dword ptr [rax+rax+00h]
0x14001093c  test    eax, eax
0x14001093e  jns     short loc_14001096E
0x140010940  mov     rcx, cs:WPP_GLOBAL_Control
0x140010947  cmp     rcx, r15
0x14001094a  jz      short loc_14001096E
0x14001094c  mov     edx, [rcx+2Ch]
0x14001094f  test    r12b, dl
0x140010952  jz      short loc_14001096E
0x140010954  cmp     byte ptr [rcx+29h], 2
0x140010958  jb      short loc_14001096E
0x14001095a  mov     rcx, [rcx+18h]
0x14001095e  mov     edx, 25h ; '%'
0x140010963  mov     r9d, eax
0x140010966  mov     r8, r13
0x140010969  call    WPP_SF_d
0x14001096e  or      dword ptr [rbx+34h], 4
0x140010972  jmp     short loc_14001099F
0x140010974  mov     rcx, cs:WPP_GLOBAL_Control
0x14001097b  cmp     rcx, r15
0x14001097e  jz      short loc_1400109CA
0x140010980  mov     eax, [rcx+2Ch]
0x140010983  test    r12b, al
0x140010986  jz      short loc_14001099F
0x140010988  cmp     byte ptr [rcx+29h], 2
0x14001098c  jb      short loc_14001099F
0x14001098e  mov     rcx, [rcx+18h]
0x140010992  mov     edx, 26h ; '&'
0x140010997  mov     r8, r13
0x14001099a  call    WPP_SF_
0x14001099f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400109a6  cmp     rcx, r15
0x1400109a9  jz      short loc_1400109CA
0x1400109ab  mov     eax, [rcx+2Ch]
0x1400109ae  test    r12b, al
0x1400109b1  jz      short loc_1400109CA
0x1400109b3  cmp     byte ptr [rcx+29h], 6
0x1400109b7  jb      short loc_1400109CA
0x1400109b9  mov     edx, 27h ; '''
0x1400109be  mov     rcx, [rcx+18h]
0x1400109c2  mov     r8, r13
0x1400109c5  call    WPP_SF_
0x1400109ca  mov     rcx, [rbp+57h+var_40]
0x1400109ce  xor     rcx, rsp; StackCookie
0x1400109d1  call    __security_check_cookie
0x1400109d6  mov     rbx, [rsp+0D0h+arg_10]
0x1400109de  add     rsp, 0A0h
0x1400109e5  pop     r15
0x1400109e7  pop     r14
0x1400109e9  pop     r13
0x1400109eb  pop     r12
0x1400109ed  pop     rdi
0x1400109ee  pop     rsi
0x1400109ef  pop     rbp
0x1400109f0  retn
```
