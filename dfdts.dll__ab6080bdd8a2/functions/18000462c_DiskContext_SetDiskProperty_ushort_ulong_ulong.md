# DiskContext::SetDiskProperty(ushort * *,ulong *,ulong)

- ea: `0x18000462c`
- end: `0x1800047e6`
- name: `?SetDiskProperty@DiskContext@@AEAAKPEAPEAGPEAKK@Z`
- size: `442`
- prototype: `__int64 __fastcall(DiskContext *this, BYTE **, unsigned int *, DWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180003e3c`
- `0x180003e8c`
- `0x180003edc`
- `0x180006c74`

## callees

- `0x180002c90`
- `0x18000462c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800046b7`
- `KERNEL32!HeapAlloc` at `0x1800046b7`
- `KERNEL32!GetProcessHeap` at `0x1800046a6`
- `KERNEL32!GetProcessHeap` at `0x1800047a9`
- `KERNEL32!GetProcessHeap` at `0x1800046a6`
- `KERNEL32!GetProcessHeap` at `0x1800047a9`
- `KERNEL32!HeapFree` at `0x1800047b7`
- `KERNEL32!HeapFree` at `0x1800047b7`
- `KERNEL32!GetLastError` at `0x18000467d`
- `KERNEL32!GetLastError` at `0x180004735`
- `KERNEL32!GetLastError` at `0x18000467d`
- `KERNEL32!GetLastError` at `0x180004735`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180004677`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000472b`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x180004677`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000472b`

## pseudocode

```c
__int64 __fastcall DiskContext::SetDiskProperty(DiskContext *this, BYTE **a2, unsigned int *a3, DWORD a4)
{
  struct _SP_DEVINFO_DATA *v6; // rdx
  void *v9; // rcx
  DWORD LastError; // ebx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *PropertyBuffer; // rdi
  BYTE *v14; // rcx
  unsigned __int64 v15; // rax
  int v16; // edx
  HANDLE v17; // rax
  DWORD RequiredSize[4]; // [rsp+40h] [rbp-38h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp+8h] BYREF

  v6 = (struct _SP_DEVINFO_DATA *)*((_QWORD *)this + 2);
  v9 = *(void **)this;
  LODWORD(dwBytes) = 0;
  *(_QWORD *)RequiredSize = 0;
  SetupDiGetDeviceRegistryPropertyW(v9, v6, a4, 0, 0, 0, (PDWORD)&dwBytes);
  LastError = GetLastError();
  if ( LastError != 122 || (unsigned int)dwBytes >= 0x7FFFFFFF )
    goto LABEL_16;
  v11 = dwBytes;
  ProcessHeap = GetProcessHeap();
  PropertyBuffer = (BYTE *)HeapAlloc(ProcessHeap, 8u, v11);
  if ( !PropertyBuffer )
  {
    LastError = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, 14);
    goto LABEL_16;
  }
  if ( !SetupDiGetDeviceRegistryPropertyW(
          *(HDEVINFO *)this,
          *((PSP_DEVINFO_DATA *)this + 2),
          a4,
          0,
          PropertyBuffer,
          dwBytes,
          RequiredSize) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, LastError);
    goto LABEL_15;
  }
  v14 = PropertyBuffer;
  v15 = (unsigned __int64)(unsigned int)dwBytes >> 1;
  v16 = v15;
  *(_QWORD *)RequiredSize = 0;
  *a2 = PropertyBuffer;
  if ( !v15 )
  {
LABEL_14:
    *(_QWORD *)RequiredSize = 0;
    LastError = v15 == 0 ? 0x57 : 0;
LABEL_15:
    v17 = GetProcessHeap();
    HeapFree(v17, 0, PropertyBuffer);
LABEL_16:
    *a3 = 0;
    return LastError;
  }
  while ( *(_WORD *)v14 )
  {
    v14 += 2;
    if ( !--v15 )
      goto LABEL_14;
  }
  LastError = 0;
  *a3 = v16 - v15;
  return LastError;
}

```

## disassembly

```asm
0x18000462c  mov     r11, rsp
0x18000462f  mov     [r11+10h], rbx
0x180004633  mov     [r11+18h], rbp
0x180004637  push    rsi
0x180004638  push    rdi
0x180004639  push    r12
0x18000463b  push    r14
0x18000463d  push    r15
0x18000463f  sub     rsp, 50h
0x180004643  xor     r12d, r12d
0x180004646  lea     rax, [r11+8]
0x18000464a  mov     ebp, r9d
0x18000464d  mov     [r11-48h], rax
0x180004651  mov     r15, rdx
0x180004654  mov     [r11-50h], r12d
0x180004658  mov     rdx, [rcx+10h]; DeviceInfoData
0x18000465c  mov     r14, r8
0x18000465f  mov     rsi, rcx
0x180004662  mov     [r11-58h], r12
0x180004666  mov     rcx, [rcx]; DeviceInfoSet
0x180004669  xor     r9d, r9d; PropertyRegDataType
0x18000466c  mov     r8d, ebp; Property
0x18000466f  mov     [r11+8], r12d
0x180004673  mov     [r11-38h], r12
0x180004677  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x18000467d  call    cs:__imp_GetLastError
0x180004683  mov     ebx, eax
0x180004685  cmp     eax, 7Ah ; 'z'
0x180004688  jnz     loc_1800047BD
0x18000468e  cmp     dword ptr [rsp+78h+dwBytes], 7FFFFFFFh
0x180004699  jnb     loc_1800047BD
0x18000469f  mov     ebx, dword ptr [rsp+78h+dwBytes]
0x1800046a6  call    cs:__imp_GetProcessHeap
0x1800046ac  mov     r8d, ebx; dwBytes
0x1800046af  lea     edx, [r12+8]; dwFlags
0x1800046b4  mov     rcx, rax; hHeap
0x1800046b7  call    cs:__imp_HeapAlloc
0x1800046bd  mov     rdi, rax
0x1800046c0  test    rax, rax
0x1800046c3  jnz     short loc_180004704
0x1800046c5  lea     ebx, [rax+0Eh]
0x1800046c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046cf  lea     rax, WPP_GLOBAL_Control
0x1800046d6  cmp     rcx, rax
0x1800046d9  jz      loc_1800047BD
0x1800046df  test    byte ptr [rcx+1Ch], 1
0x1800046e3  jz      loc_1800047BD
0x1800046e9  mov     rcx, [rcx+10h]
0x1800046ed  lea     edx, [rdi+15h]
0x1800046f0  mov     r9d, ebx
0x1800046f3  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x1800046fa  call    WPP_SF_d
0x1800046ff  jmp     loc_1800047BD
0x180004704  mov     rdx, [rsi+10h]; DeviceInfoData
0x180004708  lea     rax, [rsp+78h+var_38]
0x18000470d  mov     rcx, [rsi]; DeviceInfoSet
0x180004710  xor     r9d, r9d; PropertyRegDataType
0x180004713  mov     [rsp+78h+RequiredSize], rax; RequiredSize
0x180004718  mov     r8d, ebp; Property
0x18000471b  mov     eax, dword ptr [rsp+78h+dwBytes]
0x180004722  mov     [rsp+78h+PropertyBufferSize], eax; PropertyBufferSize
0x180004726  mov     [rsp+78h+PropertyBuffer], rdi; PropertyBuffer
0x18000472b  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x180004731  test    eax, eax
0x180004733  jnz     short loc_180004770
0x180004735  call    cs:__imp_GetLastError
0x18000473b  mov     ebx, eax
0x18000473d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004744  lea     rax, WPP_GLOBAL_Control
0x18000474b  cmp     rcx, rax
0x18000474e  jz      short loc_1800047A9
0x180004750  test    byte ptr [rcx+1Ch], 1
0x180004754  jz      short loc_1800047A9
0x180004756  mov     rcx, [rcx+10h]
0x18000475a  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004761  mov     edx, 16h
0x180004766  mov     r9d, ebx
0x180004769  call    WPP_SF_d
0x18000476e  jmp     short loc_1800047A9
0x180004770  mov     eax, dword ptr [rsp+78h+dwBytes]
0x180004777  mov     rcx, rdi
0x18000477a  shr     rax, 1
0x18000477d  mov     rdx, rax
0x180004780  mov     qword ptr [rsp+78h+var_38], r12
0x180004785  mov     [r15], rdi
0x180004788  jz      short loc_18000479A
0x18000478a  cmp     [rcx], r12w
0x18000478e  jz      short loc_1800047DB
0x180004790  add     rcx, 2
0x180004794  sub     rax, 1
0x180004798  jnz     short loc_18000478A
0x18000479a  neg     rax
0x18000479d  mov     qword ptr [rsp+78h+var_38], r12
0x1800047a2  sbb     ebx, ebx
0x1800047a4  not     ebx
0x1800047a6  and     ebx, 57h
0x1800047a9  call    cs:__imp_GetProcessHeap
0x1800047af  mov     r8, rdi; lpMem
0x1800047b2  xor     edx, edx; dwFlags
0x1800047b4  mov     rcx, rax; hHeap
0x1800047b7  call    cs:__imp_HeapFree
0x1800047bd  mov     [r14], r12d
0x1800047c0  lea     r11, [rsp+78h+var_28]
0x1800047c5  mov     eax, ebx
0x1800047c7  mov     rbx, [r11+38h]
0x1800047cb  mov     rbp, [r11+40h]
0x1800047cf  mov     rsp, r11
0x1800047d2  pop     r15
0x1800047d4  pop     r14
0x1800047d6  pop     r12
0x1800047d8  pop     rdi
0x1800047d9  pop     rsi
0x1800047da  retn
0x1800047db  sub     rdx, rax
0x1800047de  mov     ebx, r12d
0x1800047e1  mov     [r14], edx
0x1800047e4  jmp     short loc_1800047C0
```
