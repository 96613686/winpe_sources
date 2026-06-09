# ATL::CComObject<CDirFltr>::`scalar deleting destructor'(uint)

- ea: `0x1800055f0`
- end: `0x180005714`
- name: `??_G?$CComObject@VCDirFltr@@@ATL@@UEAAPEAXI@Z`
- size: `292`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800055f0`
- `0x180005720`
- `0x18000d904`
- `0x1800101c0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000570c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000570c`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180005671`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180005692`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180005671`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180005692`

## pseudocode

```c
char *__fastcall ATL::CComObject<CDirFltr>::`scalar deleting destructor'(char *Block, char a2)
{
  void *v4; // rcx
  void *v5; // rcx
  char *v6; // rcx

  *(_QWORD *)Block = &ATL::CComObject<CDirFltr>::`vftable';
  *((_DWORD *)Block + 2) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *((_QWORD *)Block + 63) = &TLMString<64,64,32767>::`vftable';
  CLMString::DeleteBuf((CLMString *)(Block + 504), (const wchar_t *)Block + 264);
  *((_QWORD *)Block + 63) = &CLMString::`vftable';
  v4 = (void *)*((_QWORD *)Block + 58);
  *((_QWORD *)Block + 58) = 0;
  if ( v4 )
    VirtualFree(v4, 0, 0x8000u);
  v5 = (void *)*((_QWORD *)Block + 56);
  *((_QWORD *)Block + 56) = 0;
  if ( v5 )
    VirtualFree(v5, 0, 0x8000u);
  v6 = (char *)*((_QWORD *)Block + 54);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  *((_QWORD *)Block + 34) = &TLMString<64,64,32767>::`vftable';
  CLMString::DeleteBuf((CLMString *)(Block + 272), (const wchar_t *)Block + 148);
  *((_QWORD *)Block + 34) = &CLMString::`vftable';
  *((_QWORD *)Block + 13) = &TLMString<64,64,32767>::`vftable';
  CLMString::DeleteBuf((CLMString *)(Block + 104), (const wchar_t *)Block + 64);
  *((_QWORD *)Block + 13) = &CLMString::`vftable';
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(Block + 16));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800055f0  push    rbx
0x1800055f2  push    rbp
0x1800055f3  push    rsi
0x1800055f4  push    rdi
0x1800055f5  push    r14
0x1800055f7  sub     rsp, 20h
0x1800055fb  mov     esi, edx
0x1800055fd  mov     rbx, rcx
0x180005600  lea     rax, ??_7?$CComObject@VCDirFltr@@@ATL@@6B@; const ATL::CComObject<CDirFltr>::`vftable'
0x180005607  mov     [rcx], rax
0x18000560a  mov     dword ptr [rcx+8], 0C0000001h
0x180005611  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005618  mov     rax, [rcx]
0x18000561b  mov     rax, [rax+10h]
0x18000561f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005624  nop
0x180005625  lea     rbp, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x18000562c  mov     [rbx+1F8h], rbp
0x180005633  lea     rdx, [rbx+210h]; wchar_t *
0x18000563a  lea     rcx, [rbx+1F8h]; this
0x180005641  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180005646  lea     r14, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18000564d  mov     [rbx+1F8h], r14
0x180005654  mov     rcx, [rbx+1D0h]; lpAddress
0x18000565b  xor     edi, edi
0x18000565d  mov     [rbx+1D0h], rdi
0x180005664  test    rcx, rcx
0x180005667  jz      short loc_180005677
0x180005669  xor     edx, edx; dwSize
0x18000566b  mov     r8d, 8000h; dwFreeType
0x180005671  call    cs:__imp_VirtualFree
0x180005677  mov     rcx, [rbx+1C0h]; lpAddress
0x18000567e  mov     [rbx+1C0h], rdi
0x180005685  test    rcx, rcx
0x180005688  jz      short loc_180005698
0x18000568a  xor     edx, edx; dwSize
0x18000568c  mov     r8d, 8000h; dwFreeType
0x180005692  call    cs:__imp_VirtualFree
0x180005698  mov     rcx, [rbx+1B0h]; hObject
0x18000569f  lea     rax, [rcx-1]
0x1800056a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800056a7  jbe     short loc_18000570C
0x1800056a9  mov     [rbx+110h], rbp
0x1800056b0  lea     rdx, [rbx+128h]; wchar_t *
0x1800056b7  lea     rcx, [rbx+110h]; this
0x1800056be  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800056c3  mov     [rbx+110h], r14
0x1800056ca  mov     [rbx+68h], rbp
0x1800056ce  lea     rdx, [rbx+80h]; wchar_t *
0x1800056d5  lea     rcx, [rbx+68h]; this
0x1800056d9  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800056de  mov     [rbx+68h], r14
0x1800056e2  lea     rcx, [rbx+10h]; this
0x1800056e6  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x1800056eb  test    sil, 1
0x1800056ef  jz      short loc_1800056FE
0x1800056f1  mov     edx, 2B0h
0x1800056f6  mov     rcx, rbx; Block
0x1800056f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800056fe  mov     rax, rbx
0x180005701  add     rsp, 20h
0x180005705  pop     r14
0x180005707  pop     rdi
0x180005708  pop     rsi
0x180005709  pop     rbp
0x18000570a  pop     rbx
0x18000570b  retn
0x18000570c  call    cs:__imp_CloseHandle
0x180005712  jmp     short loc_1800056A9
```
