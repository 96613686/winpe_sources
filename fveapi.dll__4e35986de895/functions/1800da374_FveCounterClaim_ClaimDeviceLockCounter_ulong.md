# FveCounterClaim::ClaimDeviceLockCounter(ulong)

- ea: `0x1800da374`
- end: `0x1800da4a9`
- name: `?ClaimDeviceLockCounter@FveCounterClaim@@SAJK@Z`
- size: `309`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800c935c`
- `0x1800da4b0`

## callees

- `0x180018b10`
- `0x1800da2d4`
- `0x1800da374`
- `0x1800da544`

## import_xrefs

- `bcd!BcdCloseObject` at `0x1800da47d`
- `bcd!BcdCloseObject` at `0x1800da47d`
- `bcd!BcdOpenObject` at `0x1800da406`
- `bcd!BcdOpenObject` at `0x1800da406`
- `bcd!BcdCloseStore` at `0x1800da492`
- `bcd!BcdCloseStore` at `0x1800da492`
- `bcd!BcdOpenSystemStore` at `0x1800da3de`
- `bcd!BcdOpenSystemStore` at `0x1800da3de`
- `bcd!BcdSetElementData` at `0x1800da45f`
- `bcd!BcdSetElementData` at `0x1800da45f`

## pseudocode

```c
__int64 __fastcall FveCounterClaim::ClaimDeviceLockCounter(unsigned int a1)
{
  __int64 v1; // rdi
  __int64 v2; // rdx
  int AvailableDeviceLockCounters; // ebx
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v9; // [rsp+20h] [rbp-10h] BYREF
  __int64 v10; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v11[2]; // [rsp+58h] [rbp+28h] BYREF
  __int64 v12; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  v1 = a1;
  v11[0] = 0;
  v9 = 0;
  v10 = 0;
  v13 = 0;
  v12 = 0;
  AvailableDeviceLockCounters = FveCounterClaim::GetAvailableDeviceLockCounters(v11);
  if ( AvailableDeviceLockCounters >= 0 )
  {
    v4 = 0;
    while ( v11[v4] != (_DWORD)v1 )
    {
      v4 = (unsigned int)(v4 + 1);
      if ( (_DWORD)v4 )
      {
        if ( (_DWORD)v4 == 1 )
        {
          AvailableDeviceLockCounters = -2144272179;
          goto LABEL_14;
        }
        break;
      }
    }
    v13 = v1;
    v5 = BcdOpenSystemStore(&v9, v2);
    AvailableDeviceLockCounters = FromNtStatus(v5);
    if ( AvailableDeviceLockCounters >= 0 )
    {
      v6 = BcdOpenObject(v9, &GUID_CURRENT_BOOT_ENTRY, &v12);
      AvailableDeviceLockCounters = FromNtStatus(v6);
      if ( AvailableDeviceLockCounters >= 0 )
      {
        AvailableDeviceLockCounters = FveBcdUtil::GetBcdElementData<unsigned __int64>(v12, v2, &v10);
        if ( AvailableDeviceLockCounters )
        {
          if ( AvailableDeviceLockCounters != (unsigned int)FromNtStatus(-1073741275) )
            goto LABEL_14;
        }
        else if ( v10 == v13 )
        {
          goto LABEL_14;
        }
        v7 = BcdSetElementData(v12, 620757296, &v13, 8);
        AvailableDeviceLockCounters = FromNtStatus(v7);
      }
    }
  }
LABEL_14:
  if ( v12 )
    BcdCloseObject(v12);
  if ( v9 )
    BcdCloseStore(v9, v2);
  return (unsigned int)AvailableDeviceLockCounters;
}

```

## disassembly

```asm
0x1800da374  push    rbp
0x1800da376  push    rbx
0x1800da377  push    rdi
0x1800da378  mov     rbp, rsp
0x1800da37b  sub     rsp, 30h
0x1800da37f  mov     edi, ecx
0x1800da381  lea     rcx, [rbp+arg_8]; unsigned int *
0x1800da385  mov     [rbp+arg_8], 0
0x1800da38c  mov     [rbp+var_10], 0
0x1800da394  mov     [rbp+var_8], 0
0x1800da39c  mov     [rbp+arg_18], 0
0x1800da3a4  mov     [rbp+arg_10], 0
0x1800da3ac  call    ?GetAvailableDeviceLockCounters@FveCounterClaim@@CAJPEAK@Z; FveCounterClaim::GetAvailableDeviceLockCounters(ulong *)
0x1800da3b1  mov     ebx, eax
0x1800da3b3  test    eax, eax
0x1800da3b5  js      loc_1800DA474
0x1800da3bb  xor     ecx, ecx
0x1800da3bd  cmp     [rbp+rcx*4+arg_8], edi
0x1800da3c1  jz      short loc_1800DA3D6
0x1800da3c3  inc     ecx
0x1800da3c5  cmp     ecx, 1
0x1800da3c8  jb      short loc_1800DA3BD
0x1800da3ca  jnz     short loc_1800DA3D6
0x1800da3cc  mov     ebx, 803100CDh
0x1800da3d1  jmp     loc_1800DA474
0x1800da3d6  lea     rcx, [rbp+var_10]
0x1800da3da  mov     [rbp+arg_18], rdi
0x1800da3de  call    cs:__imp_BcdOpenSystemStore
0x1800da3e5  nop     dword ptr [rax+rax+00h]
0x1800da3ea  mov     ecx, eax; int
0x1800da3ec  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da3f1  mov     ebx, eax
0x1800da3f3  test    eax, eax
0x1800da3f5  js      short loc_1800DA474
0x1800da3f7  mov     rcx, [rbp+var_10]
0x1800da3fb  lea     r8, [rbp+arg_10]
0x1800da3ff  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x1800da406  call    cs:__imp_BcdOpenObject
0x1800da40d  nop     dword ptr [rax+rax+00h]
0x1800da412  mov     ecx, eax; int
0x1800da414  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da419  mov     ebx, eax
0x1800da41b  test    eax, eax
0x1800da41d  js      short loc_1800DA474
0x1800da41f  mov     rcx, [rbp+arg_10]
0x1800da423  lea     r8, [rbp+var_8]
0x1800da427  call    ??$GetBcdElementData@_K@FveBcdUtil@@SAJPEAXKPEA_K@Z; FveBcdUtil::GetBcdElementData<unsigned __int64>(void *,ulong,unsigned __int64 *)
0x1800da42c  mov     ebx, eax
0x1800da42e  test    eax, eax
0x1800da430  jnz     short loc_1800DA43E
0x1800da432  mov     rax, [rbp+arg_18]
0x1800da436  cmp     [rbp+var_8], rax
0x1800da43a  jz      short loc_1800DA474
0x1800da43c  jmp     short loc_1800DA44C
0x1800da43e  mov     ecx, 0C0000225h; int
0x1800da443  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da448  cmp     ebx, eax
0x1800da44a  jnz     short loc_1800DA474
0x1800da44c  mov     rcx, [rbp+arg_10]
0x1800da450  lea     r8, [rbp+arg_18]
0x1800da454  mov     r9d, 8
0x1800da45a  mov     edx, 25000130h
0x1800da45f  call    cs:__imp_BcdSetElementData
0x1800da466  nop     dword ptr [rax+rax+00h]
0x1800da46b  mov     ecx, eax; int
0x1800da46d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800da472  mov     ebx, eax
0x1800da474  mov     rcx, [rbp+arg_10]
0x1800da478  test    rcx, rcx
0x1800da47b  jz      short loc_1800DA489
0x1800da47d  call    cs:__imp_BcdCloseObject
0x1800da484  nop     dword ptr [rax+rax+00h]
0x1800da489  mov     rcx, [rbp+var_10]
0x1800da48d  test    rcx, rcx
0x1800da490  jz      short loc_1800DA49E
0x1800da492  call    cs:__imp_BcdCloseStore
0x1800da499  nop     dword ptr [rax+rax+00h]
0x1800da49e  mov     eax, ebx
0x1800da4a0  add     rsp, 30h
0x1800da4a4  pop     rdi
0x1800da4a5  pop     rbx
0x1800da4a6  pop     rbp
0x1800da4a7  retn
```
