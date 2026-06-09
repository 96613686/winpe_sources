# KspCreateAutomationTableTable

- ea: `0x18004e9fc`
- end: `0x18004ebb6`
- name: `KspCreateAutomationTableTable`
- size: `442`
- prototype: `__int64 __fastcall(int, int, int, int, PKSAUTOMATION_TABLE AutomationTableB, KSOBJECT_BAG ObjectBag)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004348`
- `0x180013ea0`
- `0x18004db2c`

## callees

- `0x18000b7bc`
- `0x180019fc0`
- `0x18004e370`
- `0x18004e9fc`
- `0x18004ee10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18004eaf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004eb29`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004eaf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004eb29`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004ea54`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18004ea54`

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
0x18004e9fc  push    rbx
0x18004e9fe  push    rbp
0x18004e9ff  push    rsi
0x18004ea00  push    rdi
0x18004ea01  push    r12
0x18004ea03  push    r13
0x18004ea05  push    r14
0x18004ea07  push    r15
0x18004ea09  sub     rsp, 38h
0x18004ea0d  mov     r13, r9
0x18004ea10  mov     r15d, r8d
0x18004ea13  mov     ebp, edx
0x18004ea15  mov     rdi, rcx
0x18004ea18  xor     r14d, r14d
0x18004ea1b  lea     rax, WPP_RECORDER_INITIALIZED
0x18004ea22  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004ea29  lea     ebx, [r14+1]
0x18004ea2d  jnz     loc_18004EB59
0x18004ea33  mov     rax, rbp
0x18004ea36  mov     ecx, 0FFFFFFFFh
0x18004ea3b  shl     rax, 3
0x18004ea3f  cmp     rax, rcx
0x18004ea42  ja      loc_18004EB17
0x18004ea48  mov     r8d, 7461534Bh; Tag
0x18004ea4e  mov     edx, eax; NumberOfBytes
0x18004ea50  mov     ecx, ebx; PoolType
0x18004ea52  mov     esi, eax
0x18004ea54  call    cs:__imp_ExAllocatePoolWithTag
0x18004ea5b  nop     dword ptr [rax+rax+00h]
0x18004ea60  mov     [rdi], rax
0x18004ea63  test    rax, rax
0x18004ea66  jz      loc_18004EB1A
0x18004ea6c  mov     rcx, [rsp+78h+ObjectBag]; ObjectBag
0x18004ea74  xor     r8d, r8d; Free
0x18004ea77  mov     rdx, rax; Item
0x18004ea7a  call    KsAddItemToObjectBag
0x18004ea7f  mov     ebx, eax
0x18004ea81  test    eax, eax
0x18004ea83  js      loc_18004EB1F
0x18004ea89  mov     rcx, [rdi]; void *
0x18004ea8c  mov     r8d, esi; Size
0x18004ea8f  xor     edx, edx; Val
0x18004ea91  call    memset
0x18004ea96  test    ebp, ebp
0x18004ea98  jz      short loc_18004EB03
0x18004ea9a  mov     rsi, [rdi]
0x18004ea9d  mov     r12, r15
0x18004eaa0  mov     r15, [rsp+78h+AutomationTableB]
0x18004eaa8  mov     r14, r13
0x18004eaab  mov     rcx, [r14]
0x18004eaae  test    rcx, rcx
0x18004eab1  jz      loc_18004EB3A
0x18004eab7  mov     rdx, [rdi]
0x18004eaba  mov     rax, r13
0x18004eabd  cmp     r13, r14
0x18004eac0  jnz     loc_18004EB98
0x18004eac6  test    r15, r15
0x18004eac9  jz      loc_18004EB90
0x18004eacf  mov     r9, [rsp+78h+ObjectBag]; Bag
0x18004ead7  mov     rdx, rcx; AutomationTableA
0x18004eada  mov     rcx, rsi; AutomationTableAB
0x18004eadd  mov     r8, r15; AutomationTableB
0x18004eae0  call    KsMergeAutomationTables
0x18004eae5  mov     ebx, eax
0x18004eae7  test    ebx, ebx
0x18004eae9  jns     short loc_18004EB3D
0x18004eaeb  mov     rcx, [rdi]; P
0x18004eaee  xor     edx, edx; Tag
0x18004eaf0  call    cs:__imp_ExFreePoolWithTag
0x18004eaf7  nop     dword ptr [rax+rax+00h]
0x18004eafc  mov     qword ptr [rdi], 0
0x18004eb03  mov     eax, ebx
0x18004eb05  add     rsp, 38h
0x18004eb09  pop     r15
0x18004eb0b  pop     r14
0x18004eb0d  pop     r13
0x18004eb0f  pop     r12
0x18004eb11  pop     rdi
0x18004eb12  pop     rsi
0x18004eb13  pop     rbp
0x18004eb14  pop     rbx
0x18004eb15  retn
0x18004eb17  mov     [rdi], r14
0x18004eb1a  mov     ebx, 0C000009Ah
0x18004eb1f  mov     rcx, [rdi]; P
0x18004eb22  test    rcx, rcx
0x18004eb25  jz      short loc_18004EB03
0x18004eb27  xor     edx, edx; Tag
0x18004eb29  call    cs:__imp_ExFreePoolWithTag
0x18004eb30  nop     dword ptr [rax+rax+00h]
0x18004eb35  mov     [rdi], r14
0x18004eb38  jmp     short loc_18004EB03
0x18004eb3a  mov     [rsi], r15
0x18004eb3d  mov     ecx, 0FFFFFFFFh
0x18004eb42  add     rsi, 8
0x18004eb46  add     r14, r12
0x18004eb49  mov     eax, ebx
0x18004eb4b  add     ebp, ecx
0x18004eb4d  jnz     loc_18004EAAB
0x18004eb53  test    eax, eax
0x18004eb55  jns     short loc_18004EB03
0x18004eb57  jmp     short loc_18004EAEB
0x18004eb59  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb60  cmp     [rcx+48h], r14w
0x18004eb65  jz      loc_18004EA33
0x18004eb6b  mov     rcx, [rcx+40h]
0x18004eb6f  lea     rax, WPP_a3cb34ece7883579f6195e3273066d15_Traceguids
0x18004eb76  mov     r9d, 13h
0x18004eb7c  mov     [rsp+78h+var_58], rax
0x18004eb81  mov     r8d, ebx
0x18004eb84  mov     dl, 5
0x18004eb86  call    WPP_RECORDER_SF_
0x18004eb8b  jmp     loc_18004EA33
0x18004eb90  mov     [rsi], rcx
0x18004eb93  jmp     loc_18004EAE7
0x18004eb98  cmp     [rax], rcx
0x18004eb9b  jz      short loc_18004EBAE
0x18004eb9d  add     rdx, 8
0x18004eba1  add     rax, r12
0x18004eba4  cmp     rax, r14
0x18004eba7  jnz     short loc_18004EB98
0x18004eba9  jmp     loc_18004EAC6
0x18004ebae  mov     rax, [rdx]
0x18004ebb1  mov     [rsi], rax
0x18004ebb4  jmp     short loc_18004EB3D
```
