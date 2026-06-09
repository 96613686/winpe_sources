# InitializeVcbDeviceName

- ea: `0x1c0172498`
- end: `0x1c017270a`
- name: `InitializeVcbDeviceName`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1c016fc10`

## callees

- `0x1c000f770`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c006acc0`
- `0x1c0172498`

## import_xrefs

- `ntoskrnl!PcwCreateInstance` at `0x1c01726d5`
- `ntoskrnl!PcwCreateInstance` at `0x1c01726d5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01724fb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0172565`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01725b9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01724fb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0172565`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01725b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01726e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01807df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01726e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01807df`
- `ntoskrnl!ObQueryNameString` at `0x1c01724d0`
- `ntoskrnl!ObQueryNameString` at `0x1c0172526`
- `ntoskrnl!ObQueryNameString` at `0x1c01724d0`
- `ntoskrnl!ObQueryNameString` at `0x1c0172526`

## string_xrefs

- `0x1c0172668`: `mount.c`

## pseudocode

```c
void __fastcall InitializeVcbDeviceName(const UNICODE_STRING *a1, __int64 a2, __int64 a3)
{
  struct _OBJECT_NAME_INFORMATION *PoolWithTag; // rdi
  unsigned int NameString; // eax
  __int64 v8; // r9
  unsigned int v9; // eax
  USHORT Length; // ax
  PVOID v11; // rax
  __int16 v12; // ax
  PVOID v13; // rax
  __int64 v14; // rax
  PPCW_INSTANCE *v15; // rcx
  const UNICODE_STRING *v16; // r8
  struct _PCW_DATA *Data; // rax
  unsigned int Status; // [rsp+30h] [rbp-58h]
  struct _PCW_DATA v19; // [rsp+40h] [rbp-48h] BYREF
  __int64 v20; // [rsp+50h] [rbp-38h] BYREF
  int v21; // [rsp+58h] [rbp-30h]
  __int64 v22; // [rsp+60h] [rbp-28h] BYREF
  int v23; // [rsp+68h] [rbp-20h]
  SIZE_T NumberOfBytes; // [rsp+A8h] [rbp+20h] BYREF

  PoolWithTag = 0;
  LODWORD(NumberOfBytes) = 0;
  NameString = ObQueryNameString(*(PVOID *)(a3 + 16), 0, 0, (PULONG)&NumberOfBytes);
  v8 = NameString;
  Status = NameString;
  if ( NameString == -1073741820 )
  {
    PoolWithTag = (struct _OBJECT_NAME_INFORMATION *)ExAllocatePoolWithTag(
                                                       (POOL_TYPE)17,
                                                       (unsigned int)NumberOfBytes,
                                                       0x6F4D6552u);
    v9 = ObQueryNameString(*(PVOID *)(a3 + 16), PoolWithTag, NumberOfBytes, (PULONG)&NumberOfBytes);
    v8 = v9;
    Status = v9;
  }
  if ( (int)v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids, v8);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    v14 = RefsRaiseStatusInternal(a1, Status);
    goto LABEL_18;
  }
  a1 = (const UNICODE_STRING *)(a2 + 688);
  Length = PoolWithTag->Name.Length;
  *(_WORD *)(a2 + 688) = PoolWithTag->Name.Length;
  *(_WORD *)(a2 + 690) = Length;
  v11 = ExAllocatePoolWithTag((POOL_TYPE)17, PoolWithTag->Name.Length, 0x6F4D6552u);
  *(_QWORD *)(a2 + 696) = v11;
  memmove(v11, PoolWithTag->Name.Buffer, PoolWithTag->Name.Length);
  if ( *(_DWORD *)(a2 + 3600) == 16 )
  {
    v12 = *(_WORD *)(a3 + 6);
    *(_WORD *)(a2 + 8240) = v12;
    *(_WORD *)(a2 + 8242) = v12;
    if ( *(_WORD *)(a3 + 6) )
    {
      v13 = ExAllocatePoolWithTag((POOL_TYPE)17, *(unsigned __int16 *)(a3 + 6), 0x6F4D6552u);
      *(_QWORD *)(a2 + 8248) = v13;
      memmove(v13, (const void *)(a3 + 32), *(unsigned __int16 *)(a3 + 6));
    }
  }
  v14 = *(_QWORD *)(a2 + 3928);
  if ( v14 )
  {
    v15 = (PPCW_INSTANCE *)(a2 + 3936);
    if ( !*(_QWORD *)(a2 + 3936) )
    {
      v16 = (const UNICODE_STRING *)(a2 + 3464);
      if ( *(_WORD *)(a2 + 3464) )
      {
        v19.Data = *(const void **)(a2 + 3928);
        v19.Size = 376;
        Data = &v19;
LABEL_22:
        PcwCreateInstance(v15, CmsRefsPerfCounterSet, v16, 1u, Data);
        goto LABEL_23;
      }
LABEL_18:
      if ( *(_DWORD *)(a2 + 3600) == 16 && (v16 = (const UNICODE_STRING *)(a2 + 8240), *(_WORD *)(a2 + 8240)) )
      {
        v20 = v14;
        v21 = 376;
        Data = (struct _PCW_DATA *)&v20;
      }
      else
      {
        v22 = v14;
        v23 = 376;
        Data = (struct _PCW_DATA *)&v22;
        v16 = a1;
      }
      goto LABEL_22;
    }
  }
LABEL_23:
  ExFreePoolWithTag(PoolWithTag, 0);
}

```

## disassembly

```asm
0x1c0172498  mov     rax, rsp
0x1c017249b  mov     [rax+8], rbx
0x1c017249f  mov     [rax+10h], rsi
0x1c01724a3  push    rdi
0x1c01724a4  push    r14
0x1c01724a6  push    r15
0x1c01724a8  sub     rsp, 70h
0x1c01724ac  mov     rsi, r8
0x1c01724af  mov     rbx, rdx
0x1c01724b2  mov     r14, rcx
0x1c01724b5  xor     r15d, r15d
0x1c01724b8  mov     edi, r15d
0x1c01724bb  mov     [rax-50h], r15
0x1c01724bf  mov     [rax+20h], r15d
0x1c01724c3  lea     r9, [rax+20h]; ReturnLength
0x1c01724c7  xor     r8d, r8d; Length
0x1c01724ca  xor     edx, edx; ObjectNameInfo
0x1c01724cc  mov     rcx, [rsi+10h]; Object
0x1c01724d0  call    cs:__imp_ObQueryNameString
0x1c01724d7  nop     dword ptr [rax+rax+00h]
0x1c01724dc  mov     r9d, eax
0x1c01724df  mov     [rsp+88h+Status], eax
0x1c01724e3  cmp     eax, 0C0000004h
0x1c01724e8  jnz     short loc_1C0172539
0x1c01724ea  mov     edx, dword ptr [rsp+88h+NumberOfBytes]; NumberOfBytes
0x1c01724f1  lea     ecx, [r15+11h]; PoolType
0x1c01724f5  mov     r8d, 6F4D6552h; Tag
0x1c01724fb  call    cs:__imp_ExAllocatePoolWithTag
0x1c0172502  nop     dword ptr [rax+rax+00h]
0x1c0172507  mov     rdi, rax
0x1c017250a  mov     [rsp+88h+var_50], rax
0x1c017250f  lea     r9, [rsp+88h+NumberOfBytes]; ReturnLength
0x1c0172517  mov     r8d, dword ptr [rsp+88h+NumberOfBytes]; Length
0x1c017251f  mov     rdx, rax; ObjectNameInfo
0x1c0172522  mov     rcx, [rsi+10h]; Object
0x1c0172526  call    cs:__imp_ObQueryNameString
0x1c017252d  nop     dword ptr [rax+rax+00h]
0x1c0172532  mov     r9d, eax
0x1c0172535  mov     [rsp+88h+Status], eax
0x1c0172539  test    r9d, r9d
0x1c017253c  js      loc_1C0172621
0x1c0172542  lea     r14, [rbx+2B0h]
0x1c0172549  movzx   eax, word ptr [rdi]
0x1c017254c  mov     [r14], ax
0x1c0172550  mov     [rbx+2B2h], ax
0x1c0172557  movzx   edx, word ptr [rdi]; NumberOfBytes
0x1c017255a  mov     ecx, 11h; PoolType
0x1c017255f  mov     r8d, 6F4D6552h; Tag
0x1c0172565  call    cs:__imp_ExAllocatePoolWithTag
0x1c017256c  nop     dword ptr [rax+rax+00h]
0x1c0172571  mov     [rbx+2B8h], rax
0x1c0172578  movzx   r8d, word ptr [rdi]; Size
0x1c017257c  mov     rdx, [rdi+8]; Src
0x1c0172580  mov     rcx, rax; void *
0x1c0172583  call    memmove
0x1c0172588  cmp     dword ptr [rbx+0E10h], 10h
0x1c017258f  jnz     short loc_1C01725DD
0x1c0172591  movzx   eax, word ptr [rsi+6]
0x1c0172595  mov     [rbx+2030h], ax
0x1c017259c  mov     [rbx+2032h], ax
0x1c01725a3  movzx   eax, word ptr [rsi+6]
0x1c01725a7  test    ax, ax
0x1c01725aa  jz      short loc_1C01725DD
0x1c01725ac  mov     edx, eax; NumberOfBytes
0x1c01725ae  mov     ecx, 11h; PoolType
0x1c01725b3  mov     r8d, 6F4D6552h; Tag
0x1c01725b9  call    cs:__imp_ExAllocatePoolWithTag
0x1c01725c0  nop     dword ptr [rax+rax+00h]
0x1c01725c5  mov     [rbx+2038h], rax
0x1c01725cc  movzx   r8d, word ptr [rsi+6]; Size
0x1c01725d1  lea     rdx, [rsi+20h]; Src
0x1c01725d5  mov     rcx, rax; void *
0x1c01725d8  call    memmove
0x1c01725dd  mov     rax, [rbx+0F58h]
0x1c01725e4  test    rax, rax
0x1c01725e7  jz      loc_1C01726E2
0x1c01725ed  lea     rcx, [rbx+0F60h]
0x1c01725f4  cmp     [rcx], r15
0x1c01725f7  jnz     loc_1C01726E2
0x1c01725fd  lea     r8, [rbx+0D88h]
0x1c0172604  cmp     [r8], r15w
0x1c0172608  jbe     short loc_1C0172684
0x1c017260a  mov     [rsp+88h+var_48.Data], rax
0x1c017260f  mov     [rsp+88h+var_48.Size], 178h
0x1c0172617  lea     rax, [rsp+88h+var_48]
0x1c017261c  jmp     loc_1C01726C3
0x1c0172621  lea     rax, WPP_GLOBAL_Control
0x1c0172628  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017262f  cmp     rcx, rax
0x1c0172632  jz      short loc_1C0172658
0x1c0172634  test    dword ptr [rcx+2Ch], 100h
0x1c017263b  jz      short loc_1C0172658
0x1c017263d  cmp     byte ptr [rcx+29h], 4
0x1c0172641  jb      short loc_1C0172658
0x1c0172643  mov     edx, 2Ah ; '*'
0x1c0172648  lea     r8, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids
0x1c017264f  mov     rcx, [rcx+18h]
0x1c0172653  call    WPP_SF_D
0x1c0172658  mov     al, cs:RefsStatusDebugEnabled
0x1c017265e  test    al, al
0x1c0172660  jz      short loc_1C0172678
0x1c0172662  mov     r8d, 0ADCh
0x1c0172668  lea     rdx, aMountC; "mount.c"
0x1c017266f  mov     ecx, [rsp+88h+Status]; Status
0x1c0172673  call    RefsStatusDebug
0x1c0172678  mov     edx, [rsp+88h+Status]
0x1c017267c  mov     rcx, r14
0x1c017267f  call    RefsRaiseStatusInternal
0x1c0172684  cmp     dword ptr [rbx+0E10h], 10h
0x1c017268b  jnz     short loc_1C01726AE
0x1c017268d  lea     r8, [rbx+2030h]
0x1c0172694  cmp     [r8], r15w
0x1c0172698  jbe     short loc_1C01726AE
0x1c017269a  mov     [rsp+88h+var_38], rax
0x1c017269f  mov     [rsp+88h+var_30], 178h
0x1c01726a7  lea     rax, [rsp+88h+var_38]
0x1c01726ac  jmp     short loc_1C01726C3
0x1c01726ae  mov     [rsp+88h+var_28], rax
0x1c01726b3  mov     [rsp+88h+var_20], 178h
0x1c01726bb  lea     rax, [rsp+88h+var_28]
0x1c01726c0  mov     r8, r14; Name
0x1c01726c3  mov     [rsp+88h+Data], rax; Data
0x1c01726c8  mov     r9d, 1; Count
0x1c01726ce  mov     rdx, cs:CmsRefsPerfCounterSet; Registration
0x1c01726d5  call    cs:__imp_PcwCreateInstance
0x1c01726dc  nop     dword ptr [rax+rax+00h]
0x1c01726e1  nop
0x1c01726e2  xor     edx, edx; Tag
0x1c01726e4  mov     rcx, rdi; P
0x1c01726e7  call    cs:__imp_ExFreePoolWithTag
0x1c01726ee  nop     dword ptr [rax+rax+00h]
0x1c01726f3  lea     r11, [rsp+88h+var_18]
0x1c01726f8  mov     rbx, [r11+20h]
0x1c01726fc  mov     rsi, [r11+28h]
0x1c0172700  mov     rsp, r11
0x1c0172703  pop     r15
0x1c0172705  pop     r14
0x1c0172707  pop     rdi
0x1c0172708  retn
0x1c01807cb  push    rbp
0x1c01807cd  sub     rsp, 30h
0x1c01807d1  mov     rbp, rdx
0x1c01807d4  mov     rcx, [rbp+38h]; P
0x1c01807d8  test    rcx, rcx
0x1c01807db  jz      short loc_1C01807EC
0x1c01807dd  xor     edx, edx; Tag
0x1c01807df  call    cs:__imp_ExFreePoolWithTag
0x1c01807e6  nop     dword ptr [rax+rax+00h]
0x1c01807eb  nop
0x1c01807ec  add     rsp, 30h
0x1c01807f0  pop     rbp
0x1c01807f1  retn
```
