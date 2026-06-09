# KspCreateAutomationTableTable

- ea: `0x18004eb9c`
- end: `0x18004ed56`
- name: `KspCreateAutomationTableTable`
- size: `442`
- prototype: `__int64 __fastcall(void **, unsigned int, unsigned int, PKSAUTOMATION_TABLE *, PKSAUTOMATION_TABLE AutomationTableB, KSOBJECT_BAG ObjectBag)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004348`
- `0x180013ea0`
- `0x18004dccc`

## callees

- `0x18000b7bc`
- `0x18001a000`
- `0x18004e510`
- `0x18004eb9c`
- `0x18004efb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18004ec90`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004ecc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004ec90`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004ecc9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004ebf4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004ebf4`

## pseudocode

```c
__int64 __fastcall KspCreateAutomationTableTable(
        void **a1,
        unsigned int a2,
        unsigned int a3,
        PKSAUTOMATION_TABLE *a4,
        PKSAUTOMATION_TABLE AutomationTableB,
        KSOBJECT_BAG ObjectBag)
{
  __int64 v7; // r15
  __int64 v8; // rbp
  PVOID PoolWithTag; // rax
  NTSTATUS v11; // ebx
  PKSAUTOMATION_TABLE *v12; // rsi
  PKSAUTOMATION_TABLE *v13; // r14
  PKSAUTOMATION_TABLE v14; // rcx
  PKSAUTOMATION_TABLE *v15; // rdx
  PKSAUTOMATION_TABLE *v16; // rax

  v7 = a3;
  v8 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      19,
      (__int64)WPP_a3cb34ece7883579f6195e3273066d15_Traceguids);
  }
  if ( (unsigned __int64)(8 * v8) > 0xFFFFFFFF )
  {
    *a1 = 0;
    goto LABEL_15;
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, (unsigned int)(8 * v8), 0x7461534Bu);
  *a1 = PoolWithTag;
  if ( !PoolWithTag )
  {
LABEL_15:
    v11 = -1073741670;
    goto LABEL_16;
  }
  v11 = KsAddItemToObjectBag(ObjectBag, PoolWithTag, 0);
  if ( v11 >= 0 )
  {
    memset(*a1, 0, (unsigned int)(8 * v8));
    if ( (_DWORD)v8 )
    {
      v12 = (PKSAUTOMATION_TABLE *)*a1;
      v13 = a4;
      while ( 1 )
      {
        v14 = *v13;
        if ( *v13 )
        {
          v15 = (PKSAUTOMATION_TABLE *)*a1;
          v16 = a4;
          if ( a4 == v13 )
          {
LABEL_9:
            if ( AutomationTableB )
              v11 = KsMergeAutomationTables(v12, *v13, AutomationTableB, ObjectBag);
            else
              *v12 = v14;
            if ( v11 < 0 )
              goto LABEL_12;
          }
          else
          {
            while ( *v16 != v14 )
            {
              ++v15;
              v16 = (PKSAUTOMATION_TABLE *)((char *)v16 + v7);
              if ( v16 == v13 )
                goto LABEL_9;
            }
            *v12 = *v15;
          }
        }
        else
        {
          *v12 = AutomationTableB;
        }
        ++v12;
        v13 = (PKSAUTOMATION_TABLE *)((char *)v13 + v7);
        LODWORD(v8) = v8 - 1;
        if ( !(_DWORD)v8 )
          return (unsigned int)v11;
      }
    }
    return (unsigned int)v11;
  }
LABEL_16:
  if ( *a1 )
  {
LABEL_12:
    ExFreePoolWithTag(*a1, 0);
    *a1 = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004eb9c  push    rbx
0x18004eb9e  push    rbp
0x18004eb9f  push    rsi
0x18004eba0  push    rdi
0x18004eba1  push    r12
0x18004eba3  push    r13
0x18004eba5  push    r14
0x18004eba7  push    r15
0x18004eba9  sub     rsp, 38h
0x18004ebad  mov     r13, r9
0x18004ebb0  mov     r15d, r8d
0x18004ebb3  mov     ebp, edx
0x18004ebb5  mov     rdi, rcx
0x18004ebb8  xor     r14d, r14d
0x18004ebbb  lea     rax, WPP_RECORDER_INITIALIZED
0x18004ebc2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004ebc9  lea     ebx, [r14+1]
0x18004ebcd  jnz     loc_18004ECF9
0x18004ebd3  mov     rax, rbp
0x18004ebd6  mov     ecx, 0FFFFFFFFh
0x18004ebdb  shl     rax, 3
0x18004ebdf  cmp     rax, rcx
0x18004ebe2  ja      loc_18004ECB7
0x18004ebe8  mov     r8d, 7461534Bh; Tag
0x18004ebee  mov     edx, eax; NumberOfBytes
0x18004ebf0  mov     ecx, ebx; PoolType
0x18004ebf2  mov     esi, eax
0x18004ebf4  call    cs:__imp_ExAllocatePoolWithTag
0x18004ebfb  nop     dword ptr [rax+rax+00h]
0x18004ec00  mov     [rdi], rax
0x18004ec03  test    rax, rax
0x18004ec06  jz      loc_18004ECBA
0x18004ec0c  mov     rcx, [rsp+78h+ObjectBag]; ObjectBag
0x18004ec14  xor     r8d, r8d; Free
0x18004ec17  mov     rdx, rax; Item
0x18004ec1a  call    KsAddItemToObjectBag
0x18004ec1f  mov     ebx, eax
0x18004ec21  test    eax, eax
0x18004ec23  js      loc_18004ECBF
0x18004ec29  mov     rcx, [rdi]; void *
0x18004ec2c  mov     r8d, esi; Size
0x18004ec2f  xor     edx, edx; Val
0x18004ec31  call    memset
0x18004ec36  test    ebp, ebp
0x18004ec38  jz      short loc_18004ECA3
0x18004ec3a  mov     rsi, [rdi]
0x18004ec3d  mov     r12, r15
0x18004ec40  mov     r15, [rsp+78h+AutomationTableB]
0x18004ec48  mov     r14, r13
0x18004ec4b  mov     rcx, [r14]
0x18004ec4e  test    rcx, rcx
0x18004ec51  jz      loc_18004ECDA
0x18004ec57  mov     rdx, [rdi]
0x18004ec5a  mov     rax, r13
0x18004ec5d  cmp     r13, r14
0x18004ec60  jnz     loc_18004ED38
0x18004ec66  test    r15, r15
0x18004ec69  jz      loc_18004ED30
0x18004ec6f  mov     r9, [rsp+78h+ObjectBag]; Bag
0x18004ec77  mov     rdx, rcx; AutomationTableA
0x18004ec7a  mov     rcx, rsi; AutomationTableAB
0x18004ec7d  mov     r8, r15; AutomationTableB
0x18004ec80  call    KsMergeAutomationTables
0x18004ec85  mov     ebx, eax
0x18004ec87  test    ebx, ebx
0x18004ec89  jns     short loc_18004ECDD
0x18004ec8b  mov     rcx, [rdi]; P
0x18004ec8e  xor     edx, edx; Tag
0x18004ec90  call    cs:__imp_ExFreePoolWithTag
0x18004ec97  nop     dword ptr [rax+rax+00h]
0x18004ec9c  mov     qword ptr [rdi], 0
0x18004eca3  mov     eax, ebx
0x18004eca5  add     rsp, 38h
0x18004eca9  pop     r15
0x18004ecab  pop     r14
0x18004ecad  pop     r13
0x18004ecaf  pop     r12
0x18004ecb1  pop     rdi
0x18004ecb2  pop     rsi
0x18004ecb3  pop     rbp
0x18004ecb4  pop     rbx
0x18004ecb5  retn
0x18004ecb7  mov     [rdi], r14
0x18004ecba  mov     ebx, 0C000009Ah
0x18004ecbf  mov     rcx, [rdi]; P
0x18004ecc2  test    rcx, rcx
0x18004ecc5  jz      short loc_18004ECA3
0x18004ecc7  xor     edx, edx; Tag
0x18004ecc9  call    cs:__imp_ExFreePoolWithTag
0x18004ecd0  nop     dword ptr [rax+rax+00h]
0x18004ecd5  mov     [rdi], r14
0x18004ecd8  jmp     short loc_18004ECA3
0x18004ecda  mov     [rsi], r15
0x18004ecdd  mov     ecx, 0FFFFFFFFh
0x18004ece2  add     rsi, 8
0x18004ece6  add     r14, r12
0x18004ece9  mov     eax, ebx
0x18004eceb  add     ebp, ecx
0x18004eced  jnz     loc_18004EC4B
0x18004ecf3  test    eax, eax
0x18004ecf5  jns     short loc_18004ECA3
0x18004ecf7  jmp     short loc_18004EC8B
0x18004ecf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed00  cmp     [rcx+48h], r14w
0x18004ed05  jz      loc_18004EBD3
0x18004ed0b  mov     rcx, [rcx+40h]
0x18004ed0f  lea     rax, WPP_a3cb34ece7883579f6195e3273066d15_Traceguids
0x18004ed16  mov     r9d, 13h
0x18004ed1c  mov     [rsp+78h+var_58], rax
0x18004ed21  mov     r8d, ebx
0x18004ed24  mov     dl, 5
0x18004ed26  call    WPP_RECORDER_SF_
0x18004ed2b  jmp     loc_18004EBD3
0x18004ed30  mov     [rsi], rcx
0x18004ed33  jmp     loc_18004EC87
0x18004ed38  cmp     [rax], rcx
0x18004ed3b  jz      short loc_18004ED4E
0x18004ed3d  add     rdx, 8
0x18004ed41  add     rax, r12
0x18004ed44  cmp     rax, r14
0x18004ed47  jnz     short loc_18004ED38
0x18004ed49  jmp     loc_18004EC66
0x18004ed4e  mov     rax, [rdx]
0x18004ed51  mov     [rsi], rax
0x18004ed54  jmp     short loc_18004ECDD
```
