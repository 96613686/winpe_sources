# CMSDiscMasterObj::~CMSDiscMasterObj(void)

- ea: `0x18000b394`
- end: `0x18000b3ef`
- name: `??1CMSDiscMasterObj@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(CMSDiscMasterObj *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180007e90`
- `0x180007f70`

## callees

- `0x18000b394`
- `0x1800109d0`
- `0x1800150f8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000b3b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3b0`
- `KERNEL32!DeleteCriticalSection` at `0x18000b3e3`
- `KERNEL32!DeleteCriticalSection` at `0x18000b3e3`

## pseudocode

```c
void __fastcall CMSDiscMasterObj::~CMSDiscMasterObj(CMSDiscMasterObj *this)
{
  bool v2; // zf

  CRedbookTracks::~CRedbookTracks((BSTR *)this + 64);
  SysFreeString(*((BSTR *)this + 55));
  v2 = *((_DWORD *)this + 51) == 0;
  *((_QWORD *)this + 24) = &CMyUpdateList::`vftable';
  if ( !v2 )
    CMyUpdateList::RemoveAll((CMSDiscMasterObj *)((char *)this + 192));
  if ( *((_BYTE *)this + 176) )
  {
    *((_BYTE *)this + 176) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  }
}

```

## disassembly

```asm
0x18000b394  push    rbx
0x18000b396  sub     rsp, 20h
0x18000b39a  mov     rbx, rcx
0x18000b39d  add     rcx, 200h; this
0x18000b3a4  call    ??1CRedbookTracks@@QEAA@XZ; CRedbookTracks::~CRedbookTracks(void)
0x18000b3a9  mov     rcx, [rbx+1B8h]; bstrString
0x18000b3b0  call    cs:__imp_SysFreeString
0x18000b3b6  lea     rcx, [rbx+0C0h]; this
0x18000b3bd  cmp     dword ptr [rcx+0Ch], 0
0x18000b3c1  lea     rax, ??_7CMyUpdateList@@6B@; const CMyUpdateList::`vftable'
0x18000b3c8  mov     [rcx], rax
0x18000b3cb  jz      short loc_18000B3D2
0x18000b3cd  call    ?RemoveAll@CMyUpdateList@@QEAAEXZ; CMyUpdateList::RemoveAll(void)
0x18000b3d2  lea     rcx, [rbx+88h]; lpCriticalSection
0x18000b3d9  cmp     byte ptr [rcx+28h], 0
0x18000b3dd  jz      short loc_18000B3E9
0x18000b3df  mov     byte ptr [rcx+28h], 0
0x18000b3e3  call    cs:__imp_DeleteCriticalSection
0x18000b3e9  add     rsp, 20h
0x18000b3ed  pop     rbx
0x18000b3ee  retn
```
