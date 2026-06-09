# lldpReadComputerName

- ea: `0x140013810`
- end: `0x140013a71`
- name: `lldpReadComputerName`
- size: `609`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004a60`
- `0x140004b00`
- `0x14000574c`
- `0x1400057c0`
- `0x140013810`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001398b`
- `ntoskrnl!ExAllocatePool2` at `0x14001398b`
- `ntoskrnl!RtlUnicodeToUTF8N` at `0x1400138c3`
- `ntoskrnl!RtlUnicodeToUTF8N` at `0x1400139f3`
- `ntoskrnl!RtlUnicodeToUTF8N` at `0x1400138c3`
- `ntoskrnl!RtlUnicodeToUTF8N` at `0x1400139f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013a4b`

## pseudocode

```c
__int64 __fastcall lldpReadComputerName(__int64 a1, unsigned int a2, const WCHAR *a3, ULONG a4)
{
  unsigned int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  void *Pool2; // rax
  unsigned int v13; // eax
  ULONG UTF8StringActualByteCount; // [rsp+48h] [rbp+10h] BYREF

  UTF8StringActualByteCount = 0;
  if ( a2 - 1 <= 1 )
  {
    while ( a4 >= 2 )
    {
      if ( a3[((unsigned __int64)a4 >> 1) - 1] )
        goto LABEL_13;
      a4 -= 2;
    }
    if ( !a4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids);
      return 3221225762LL;
    }
LABEL_13:
    v7 = RtlUnicodeToUTF8N(0, 0, &UTF8StringActualByteCount, a3, a4);
    v9 = v7;
    if ( v7 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v11 = 12;
LABEL_33:
        WPP_SF_d(v10->AttachedDevice, v11, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids, v9);
      }
    }
    else
    {
      if ( UTF8StringActualByteCount > 0xFF )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_sDD(
            WPP_GLOBAL_Control->AttachedDevice,
            UTF8StringActualByteCount,
            v8,
            (_DWORD)a3,
            UTF8StringActualByteCount);
        return 0;
      }
      if ( !UTF8StringActualByteCount )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, UTF8StringActualByteCount, v8, a3);
        return 0;
      }
      LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) = UTF8StringActualByteCount;
      Pool2 = (void *)ExAllocatePool2(64, UTF8StringActualByteCount, 1346653260);
      WPP_MAIN_CB.Dpc.DpcData = Pool2;
      if ( !Pool2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids);
        return 0;
      }
      v13 = RtlUnicodeToUTF8N((PCHAR)Pool2, (ULONG)WPP_MAIN_CB.Dpc.SystemArgument2, &UTF8StringActualByteCount, a3, a4);
      v9 = v13;
      if ( !v13 )
        return 0;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v11 = 16;
        goto LABEL_33;
      }
    }
    LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) = 0;
    if ( WPP_MAIN_CB.Dpc.DpcData )
    {
      ExFreePoolWithTag(WPP_MAIN_CB.Dpc.DpcData, 0x50444C4Cu);
      WPP_MAIN_CB.Dpc.DpcData = 0;
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids, a2);
  return 3221225762LL;
}

```

## disassembly

```asm
0x140013810  mov     [rsp+arg_0], rbx
0x140013815  mov     [rsp+arg_10], rsi
0x14001381a  push    rdi
0x14001381b  sub     rsp, 30h
0x14001381f  xor     esi, esi
0x140013821  lea     eax, [rdx-1]
0x140013824  mov     [rsp+38h+UTF8StringActualByteCount], esi
0x140013828  mov     ebx, r9d
0x14001382b  mov     rdi, r8
0x14001382e  mov     r9d, edx
0x140013831  cmp     eax, 1
0x140013834  jbe     short loc_140013874
0x140013836  mov     rcx, cs:WPP_GLOBAL_Control
0x14001383d  lea     rax, WPP_GLOBAL_Control
0x140013844  cmp     rcx, rax
0x140013847  jz      short loc_1400138A9
0x140013849  cmp     byte ptr [rcx+29h], 2
0x14001384d  jb      short loc_1400138A9
0x14001384f  mov     rcx, [rcx+18h]
0x140013853  lea     edx, [rsi+0Ah]
0x140013856  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x14001385d  call    WPP_SF_d
0x140013862  jmp     short loc_1400138A9
0x140013864  mov     eax, ebx
0x140013866  shr     rax, 1
0x140013869  cmp     [r8+rax*2-2], si
0x14001386f  jnz     short loc_1400138B3
0x140013871  add     ebx, 0FFFFFFFEh
0x140013874  cmp     ebx, 2
0x140013877  jnb     short loc_140013864
0x140013879  test    ebx, ebx
0x14001387b  jnz     short loc_1400138B3
0x14001387d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013884  lea     rax, WPP_GLOBAL_Control
0x14001388b  cmp     rcx, rax
0x14001388e  jz      short loc_1400138A9
0x140013890  cmp     byte ptr [rcx+29h], 2
0x140013894  jb      short loc_1400138A9
0x140013896  mov     rcx, [rcx+18h]
0x14001389a  lea     edx, [rbx+0Bh]
0x14001389d  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x1400138a4  call    WPP_SF_
0x1400138a9  mov     eax, 0C0000122h
0x1400138ae  jmp     loc_140013A60
0x1400138b3  mov     r9, rdi; UnicodeStringSource
0x1400138b6  mov     [rsp+38h+UnicodeStringByteCount], ebx; UnicodeStringByteCount
0x1400138ba  lea     r8, [rsp+38h+UTF8StringActualByteCount]; UTF8StringActualByteCount
0x1400138bf  xor     edx, edx; UTF8StringMaxByteCount
0x1400138c1  xor     ecx, ecx; UTF8StringDestination
0x1400138c3  call    cs:__imp_RtlUnicodeToUTF8N
0x1400138ca  nop     dword ptr [rax+rax+00h]
0x1400138cf  mov     r9d, eax
0x1400138d2  test    eax, eax
0x1400138d4  jz      short loc_140013901
0x1400138d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400138dd  lea     rax, WPP_GLOBAL_Control
0x1400138e4  cmp     rcx, rax
0x1400138e7  jz      loc_140013A34
0x1400138ed  cmp     byte ptr [rcx+29h], 2
0x1400138f1  jb      loc_140013A34
0x1400138f7  mov     edx, 0Ch
0x1400138fc  jmp     loc_140013A24
0x140013901  mov     edx, [rsp+38h+UTF8StringActualByteCount]
0x140013905  cmp     edx, 0FFh
0x14001390b  jbe     short loc_140013943
0x14001390d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013914  lea     rax, WPP_GLOBAL_Control
0x14001391b  cmp     rcx, rax
0x14001391e  jz      loc_140013A5E
0x140013924  cmp     byte ptr [rcx+29h], 2
0x140013928  jb      loc_140013A5E
0x14001392e  mov     rcx, [rcx+18h]
0x140013932  mov     r9, rdi
0x140013935  mov     [rsp+38h+UnicodeStringByteCount], edx
0x140013939  call    WPP_SF_sDD
0x14001393e  jmp     loc_140013A5E
0x140013943  cmp     edx, 1
0x140013946  jnb     short loc_14001397A
0x140013948  mov     rcx, cs:WPP_GLOBAL_Control
0x14001394f  lea     rax, WPP_GLOBAL_Control
0x140013956  cmp     rcx, rax
0x140013959  jz      loc_140013A5E
0x14001395f  cmp     byte ptr [rcx+29h], 2
0x140013963  jb      loc_140013A5E
0x140013969  mov     rcx, [rcx+18h]
0x14001396d  mov     r9, rdi
0x140013970  call    WPP_SF_s
0x140013975  jmp     loc_140013A5E
0x14001397a  mov     ecx, 40h ; '@'
0x14001397f  mov     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2, edx
0x140013985  mov     r8d, 50444C4Ch
0x14001398b  call    cs:__imp_ExAllocatePool2
0x140013992  nop     dword ptr [rax+rax+00h]
0x140013997  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rax
0x14001399e  test    rax, rax
0x1400139a1  jnz     short loc_1400139DE
0x1400139a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400139aa  lea     rax, WPP_GLOBAL_Control
0x1400139b1  cmp     rcx, rax
0x1400139b4  jz      loc_140013A5E
0x1400139ba  cmp     byte ptr [rcx+29h], 2
0x1400139be  jb      loc_140013A5E
0x1400139c4  mov     rcx, [rcx+18h]
0x1400139c8  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x1400139cf  mov     edx, 0Fh
0x1400139d4  call    WPP_SF_
0x1400139d9  jmp     loc_140013A5E
0x1400139de  mov     edx, dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2; UTF8StringMaxByteCount
0x1400139e4  lea     r8, [rsp+38h+UTF8StringActualByteCount]; UTF8StringActualByteCount
0x1400139e9  mov     r9, rdi; UnicodeStringSource
0x1400139ec  mov     [rsp+38h+UnicodeStringByteCount], ebx; UnicodeStringByteCount
0x1400139f0  mov     rcx, rax; UTF8StringDestination
0x1400139f3  call    cs:__imp_RtlUnicodeToUTF8N
0x1400139fa  nop     dword ptr [rax+rax+00h]
0x1400139ff  mov     r9d, eax
0x140013a02  test    eax, eax
0x140013a04  jz      short loc_140013A5E
0x140013a06  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a0d  lea     rax, WPP_GLOBAL_Control
0x140013a14  cmp     rcx, rax
0x140013a17  jz      short loc_140013A34
0x140013a19  cmp     byte ptr [rcx+29h], 2
0x140013a1d  jb      short loc_140013A34
0x140013a1f  mov     edx, 10h
0x140013a24  mov     rcx, [rcx+18h]
0x140013a28  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x140013a2f  call    WPP_SF_d
0x140013a34  mov     rcx, cs:WPP_MAIN_CB.Dpc.DpcData; P
0x140013a3b  mov     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2, esi
0x140013a41  test    rcx, rcx
0x140013a44  jz      short loc_140013A5E
0x140013a46  mov     edx, 50444C4Ch; Tag
0x140013a4b  call    cs:__imp_ExFreePoolWithTag
0x140013a52  nop     dword ptr [rax+rax+00h]
0x140013a57  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rsi
0x140013a5e  xor     eax, eax
0x140013a60  mov     rbx, [rsp+38h+arg_0]
0x140013a65  mov     rsi, [rsp+38h+arg_10]
0x140013a6a  add     rsp, 30h
0x140013a6e  pop     rdi
0x140013a6f  retn
```
