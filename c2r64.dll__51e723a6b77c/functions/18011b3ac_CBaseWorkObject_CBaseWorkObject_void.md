# CBaseWorkObject::~CBaseWorkObject(void)

- ea: `0x18011b3ac`
- end: `0x18011b53e`
- name: `??1CBaseWorkObject@@UEAA@XZ`
- size: `402`
- prototype: `void __fastcall(CBaseWorkObject *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801148e8`
- `0x1801184b0`
- `0x18011ae94`
- `0x18011b580`

## callees

- `0x180013c78`
- `0x1800264b4`
- `0x1801069a0`
- `0x18011834c`
- `0x18011b3ac`
- `0x18011cb60`
- `0x180146090`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18011b52d`
- `KERNEL32!DeleteCriticalSection` at `0x18011b52d`
- `KERNEL32!ResetEvent` at `0x18011b4c6`
- `KERNEL32!ResetEvent` at `0x18011b4c6`
- `KERNEL32!InterlockedPopEntrySList` at `0x18011b476`
- `KERNEL32!InterlockedPopEntrySList` at `0x18011b476`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBaseWorkObject::~CBaseWorkObject(CBaseWorkObject *this)
{
  __int64 v2; // rdi
  PSLIST_ENTRY v3; // r8
  void *v5; // rcx
  __int64 v6; // rcx

  if ( (*((_DWORD *)this + 8) & 0x3FFF) != 0 )
    MsoShipAssertTagProc(507552784);
  if ( (*((_DWORD *)this + 8) & 0xFFFC000) != 0 )
    MsoShipAssertTagProc(507552783);
  if ( (*((_DWORD *)this + 8) & 0x10000000) != 0 )
    MsoShipAssertTagProc(507552782);
  if ( (*((_DWORD *)this + 8) & 0x20000000) != 0 )
    MsoShipAssertTagProc(507552781);
  if ( *((int *)this + 8) < 0 )
    MsoShipAssertTagProc(507552780);
  if ( (Microsoft_Office_ThreadpoolEnableBits & 1) != 0 )
    McTemplateU0p_EventWriteTransfer(guidProviderOfficeThreadpool_Context, TPWorkObjectDestroy, this);
  if ( *((_DWORD *)this + 38) )
    CThreadReservation::ReleaseUser(*((CThreadReservation **)this + 18));
  SafeRelease<CTpWorkObject>((char *)this + 144);
  if ( *((_DWORD *)this + 34) )
  {
    while ( 1 )
    {
      v2 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL);
      if ( (unsigned __int64)*(unsigned int *)(v2 + 72) < *(_QWORD *)(v2 + 64) )
        goto LABEL_20;
      v3 = InterlockedPopEntrySList((PSLIST_HEADER)(v2 + 16));
      if ( !v3 )
        break;
      (*(void (__fastcall **)(_QWORD, PSLIST_ENTRY))(**(_QWORD **)(v2 + 32) + 32LL))(*(_QWORD *)(v2 + 32), v3);
LABEL_21:
      if ( (*((_DWORD *)this + 34))-- == 1 )
        goto LABEL_22;
    }
    MsoShipAssertTagProc(507553378);
LABEL_20:
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 72));
    goto LABEL_21;
  }
LABEL_22:
  v5 = (void *)*((_QWORD *)this + 23);
  if ( v5 )
  {
    if ( *((_BYTE *)this + 194) )
      ResetEvent(v5);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 5) + 80LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 5) + 80LL),
      *((_QWORD *)this + 23));
  }
  if ( *((_QWORD *)this + 16) && (*((_BYTE *)this + 60) & 4) == 0 )
    CBaseWorkObject::ReleaseCallback(this);
  *((_QWORD *)this + 16) = 0;
  v6 = *((_QWORD *)this + 6);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 6) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
}

```

## disassembly

```asm
0x18011b3ac  mov     [rsp+arg_8], rbx
0x18011b3b1  push    rdi
0x18011b3b2  sub     rsp, 20h
0x18011b3b6  mov     rbx, rcx
0x18011b3b9  mov     eax, [rcx+20h]
0x18011b3bc  test    eax, 3FFFh
0x18011b3c1  jz      short loc_18011B3CD
0x18011b3c3  mov     ecx, 1E40A410h
0x18011b3c8  call    MsoShipAssertTagProc
0x18011b3cd  mov     eax, [rbx+20h]
0x18011b3d0  test    eax, 0FFFC000h
0x18011b3d5  jz      short loc_18011B3E1
0x18011b3d7  mov     ecx, 1E40A40Fh
0x18011b3dc  call    MsoShipAssertTagProc
0x18011b3e1  mov     eax, [rbx+20h]
0x18011b3e4  bt      eax, 1Ch
0x18011b3e8  jnb     short loc_18011B3F4
0x18011b3ea  mov     ecx, 1E40A40Eh
0x18011b3ef  call    MsoShipAssertTagProc
0x18011b3f4  mov     eax, [rbx+20h]
0x18011b3f7  bt      eax, 1Dh
0x18011b3fb  jnb     short loc_18011B407
0x18011b3fd  mov     ecx, 1E40A40Dh
0x18011b402  call    MsoShipAssertTagProc
0x18011b407  mov     eax, [rbx+20h]
0x18011b40a  test    eax, eax
0x18011b40c  jns     short loc_18011B418
0x18011b40e  mov     ecx, 1E40A40Ch
0x18011b413  call    MsoShipAssertTagProc
0x18011b418  test    cs:Microsoft_Office_ThreadpoolEnableBits, 1
0x18011b41f  jz      short loc_18011B437
0x18011b421  mov     r8, rbx
0x18011b424  lea     rdx, TPWorkObjectDestroy
0x18011b42b  lea     rcx, guidProviderOfficeThreadpool_Context
0x18011b432  call    McTemplateU0p_EventWriteTransfer
0x18011b437  lea     rdi, [rbx+90h]
0x18011b43e  mov     eax, [rbx+98h]
0x18011b444  test    eax, eax
0x18011b446  jz      short loc_18011B450
0x18011b448  mov     rcx, [rdi]; this
0x18011b44b  call    ?ReleaseUser@CThreadReservation@@QEAAXXZ; CThreadReservation::ReleaseUser(void)
0x18011b450  mov     rcx, rdi
0x18011b453  call    ??$SafeRelease@VCTpWorkObject@@@@YAXAEAPEAVCTpWorkObject@@@Z; SafeRelease<CTpWorkObject>(CTpWorkObject * &)
0x18011b458  cmp     dword ptr [rbx+88h], 0
0x18011b45f  jbe     short loc_18011B4B1
0x18011b461  mov     rax, [rbx+30h]
0x18011b465  mov     rdi, [rax+8]
0x18011b469  mov     eax, [rdi+48h]
0x18011b46c  cmp     rax, [rdi+40h]
0x18011b470  jb      short loc_18011B4A4
0x18011b472  lea     rcx, [rdi+10h]; ListHead
0x18011b476  call    cs:__imp_InterlockedPopEntrySList
0x18011b47c  mov     r8, rax
0x18011b47f  test    rax, rax
0x18011b482  jz      short loc_18011B49A
0x18011b484  mov     rcx, [rdi+20h]
0x18011b488  mov     rdx, [rcx]
0x18011b48b  mov     rax, [rdx+20h]
0x18011b48f  mov     rdx, r8
0x18011b492  call    cs:__guard_dispatch_icall_fptr
0x18011b498  jmp     short loc_18011B4A8
0x18011b49a  mov     ecx, 1E40A662h
0x18011b49f  call    MsoShipAssertTagProc
0x18011b4a4  lock inc dword ptr [rdi+48h]
0x18011b4a8  add     dword ptr [rbx+88h], 0FFFFFFFFh
0x18011b4af  jnz     short loc_18011B461
0x18011b4b1  mov     rcx, [rbx+0B8h]; hEvent
0x18011b4b8  test    rcx, rcx
0x18011b4bb  jz      short loc_18011B4E8
0x18011b4bd  cmp     byte ptr [rbx+0C2h], 0
0x18011b4c4  jz      short loc_18011B4CC
0x18011b4c6  call    cs:__imp_ResetEvent
0x18011b4cc  mov     rax, [rbx+28h]
0x18011b4d0  mov     rcx, [rax+50h]
0x18011b4d4  mov     rax, [rcx]
0x18011b4d7  mov     rdx, [rbx+0B8h]
0x18011b4de  mov     rax, [rax+20h]
0x18011b4e2  call    cs:__guard_dispatch_icall_fptr
0x18011b4e8  cmp     qword ptr [rbx+80h], 0
0x18011b4f0  jz      short loc_18011B500
0x18011b4f2  test    byte ptr [rbx+3Ch], 4
0x18011b4f6  jnz     short loc_18011B500
0x18011b4f8  mov     rcx, rbx; this
0x18011b4fb  call    ?ReleaseCallback@CBaseWorkObject@@QEAAXXZ; CBaseWorkObject::ReleaseCallback(void)
0x18011b500  mov     qword ptr [rbx+80h], 0
0x18011b50b  mov     rcx, [rbx+30h]
0x18011b50f  test    rcx, rcx
0x18011b512  jz      short loc_18011B529
0x18011b514  mov     rax, [rcx]
0x18011b517  mov     rax, [rax+10h]
0x18011b51b  call    cs:__guard_dispatch_icall_fptr
0x18011b521  mov     qword ptr [rbx+30h], 0
0x18011b529  lea     rcx, [rbx+48h]; lpCriticalSection
0x18011b52d  call    cs:__imp_DeleteCriticalSection
0x18011b533  mov     rbx, [rsp+28h+arg_8]
0x18011b538  add     rsp, 20h
0x18011b53c  pop     rdi
0x18011b53d  retn
```
