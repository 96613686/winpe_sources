# CEnumEventObject::Reset(void)

- ea: `0x180010100`
- end: `0x1800101fc`
- name: `?Reset@CEnumEventObject@@UEAAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(CEnumEventObject *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003d54`
- `0x180010100`
- `0x180010410`
- `0x180023d88`
- `0x18003ecb0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001019c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800101e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001019c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800101e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010185`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010185`

## string_xrefs

- `0x18001013d`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
__int64 __fastcall CEnumEventObject::Reset(CEnumEventObject *this)
{
  CSemExclusiveES *v2; // rdi
  void (__fastcall ***v3)(_QWORD); // rcx
  _QWORD *v4; // rax
  __int64 v6; // rcx
  unsigned int v7; // [rsp+20h] [rbp-28h]

  v7 = 0;
  v2 = (CSemExclusiveES *)(*((_QWORD *)this + 2) + 104LL);
  if ( *((_QWORD *)this + 2) == -104 )
    InternalError(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x158u, 0x80001203, 0x10u);
  CSemExclusiveES::Lock(v2);
  v3 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 3);
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 68LL) )
  {
    if ( v3 )
    {
      (**v3)(v3);
    }
    else
    {
      v4 = CoTaskMemAlloc(0x18u);
      if ( v4 )
      {
        v6 = *((_QWORD *)this + 2) + 56LL;
        *v4 = &Enum::`vftable';
        *v4 = &EnumMap<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::`vftable';
        v4[1] = v6;
        v4[2] = v6 + 24;
      }
      *((_QWORD *)this + 3) = v4;
      if ( !v4 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)v2);
        return 2147942414LL;
      }
    }
  }
  else
  {
    if ( v3 )
    {
      EnumMap<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::`scalar deleting destructor'(v3);
      *((_QWORD *)this + 3) = 0;
    }
    v7 = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
  return v7;
}

```

## disassembly

```asm
0x180010100  mov     [rsp+arg_0], rbx
0x180010105  push    rdi
0x180010106  sub     rsp, 40h
0x18001010a  mov     rbx, rcx
0x18001010d  mov     [rsp+48h+var_28], 0
0x180010115  mov     rdi, [rcx+10h]
0x180010119  add     rdi, 68h ; 'h'
0x18001011d  mov     [rsp+48h+var_20], 1
0x180010125  mov     [rsp+48h+var_18], rdi
0x18001012a  jnz     short loc_180010149
0x18001012c  mov     edx, 158h; unsigned int
0x180010131  mov     r9d, 10h; unsigned __int16
0x180010137  mov     r8d, 80001203h; unsigned int
0x18001013d  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x180010144  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180010149  mov     rcx, rdi; this
0x18001014c  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x180010151  mov     rcx, [rbx+18h]; pv
0x180010155  mov     rax, [rbx+10h]
0x180010159  cmp     dword ptr [rax+44h], 0
0x18001015d  jnz     short loc_18001016E
0x18001015f  test    rcx, rcx
0x180010162  jnz     short loc_1800101D3
0x180010164  mov     [rsp+48h+var_28], 1
0x18001016c  jmp     short loc_1800101E2
0x18001016e  test    rcx, rcx
0x180010171  jz      short loc_180010180
0x180010173  mov     rax, [rcx]
0x180010176  mov     rax, [rax]
0x180010179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001017e  jmp     short loc_1800101E2
0x180010180  mov     ecx, 18h; cb
0x180010185  call    cs:__imp_CoTaskMemAlloc
0x18001018b  test    rax, rax
0x18001018e  jnz     short loc_1800101A9
0x180010190  mov     [rbx+18h], rax
0x180010194  test    rax, rax
0x180010197  jnz     short loc_1800101E2
0x180010199  mov     rcx, rdi; lpCriticalSection
0x18001019c  call    cs:__imp_LeaveCriticalSection
0x1800101a2  mov     eax, 8007000Eh
0x1800101a7  jmp     short loc_1800101F1
0x1800101a9  mov     rcx, [rbx+10h]
0x1800101ad  add     rcx, 38h ; '8'
0x1800101b1  lea     rdx, ??_7Enum@@6B@; const Enum::`vftable'
0x1800101b8  mov     [rax], rdx
0x1800101bb  lea     rdx, ??_7?$EnumMap@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@6B@; const EnumMap<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::`vftable'
0x1800101c2  mov     [rax], rdx
0x1800101c5  mov     [rax+8], rcx
0x1800101c9  add     rcx, 18h
0x1800101cd  mov     [rax+10h], rcx
0x1800101d1  jmp     short loc_180010190
0x1800101d3  call    ??_G?$EnumMap@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@QEAAPEAXI@Z; EnumMap<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::`scalar deleting destructor'(uint)
0x1800101d8  mov     qword ptr [rbx+18h], 0
0x1800101e0  jmp     short loc_180010164
0x1800101e2  mov     rcx, rdi; lpCriticalSection
0x1800101e5  call    cs:__imp_LeaveCriticalSection
0x1800101eb  jmp     short $+2
0x1800101ed  mov     eax, [rsp+48h+var_28]
0x1800101f1  mov     rbx, [rsp+48h+arg_0]
0x1800101f6  add     rsp, 40h
0x1800101fa  pop     rdi
0x1800101fb  retn
0x180043e2e  push    rbp
0x180043e30  sub     rsp, 20h
0x180043e34  mov     rbp, rdx
0x180043e37  lea     rdx, [rbp+20h]; int *
0x180043e3b  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180043e40  nop
0x180043e41  add     rsp, 20h
0x180043e45  pop     rbp
0x180043e46  retn
```
