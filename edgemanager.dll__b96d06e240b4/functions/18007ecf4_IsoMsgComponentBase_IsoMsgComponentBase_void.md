# IsoMsgComponentBase::~IsoMsgComponentBase(void)

- ea: `0x18007ecf4`
- end: `0x18007ed6b`
- name: `??1IsoMsgComponentBase@@MEAA@XZ`
- size: `119`
- prototype: `void __fastcall(IsoMsgComponentBase *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006784c`
- `0x180067910`

## callees

- `0x18007ecf4`

## import_xrefs

- `edgeIso!__imp_?IsoLockArtifact@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18007ed30`
- `edgeIso!__imp_?IsoLockArtifact@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18007ed30`
- `edgeIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18007ed50`
- `edgeIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18007ed50`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18007ed59`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18007ed59`
- `edgeIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x18007ed1a`
- `edgeIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x18007ed1a`

## pseudocode

```c
void __fastcall IsoMsgComponentBase::~IsoMsgComponentBase(IsoMsgComponentBase *this)
{
  unsigned int CurrentThreadHandle; // edi
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &IsoMsgComponentBase::`vftable';
  if ( *((_DWORD *)this + 2) )
  {
    v3 = 0;
    CurrentThreadHandle = IsoGetCurrentThreadHandle();
    if ( (int)IsoLockArtifact(CurrentThreadHandle, 3, &v3) >= 0 )
    {
      if ( *(_DWORD *)(v3 + 48) == *((_DWORD *)this + 2) )
        *(_DWORD *)(v3 + 48) = 0;
      IsoUnlockArtifact(CurrentThreadHandle);
    }
    IsoRemoveArtifact(*((_DWORD *)this + 2));
  }
}

```

## disassembly

```asm
0x18007ecf4  mov     [rsp+arg_8], rbx
0x18007ecf9  push    rdi
0x18007ecfa  sub     rsp, 20h
0x18007ecfe  mov     rbx, rcx
0x18007ed01  lea     rax, ??_7IsoMsgComponentBase@@6B@; const IsoMsgComponentBase::`vftable'
0x18007ed08  mov     [rcx], rax
0x18007ed0b  cmp     dword ptr [rcx+8], 0
0x18007ed0f  jz      short loc_18007ED60
0x18007ed11  mov     [rsp+28h+arg_0], 0
0x18007ed1a  call    cs:__imp_?IsoGetCurrentThreadHandle@@YAKXZ; IsoGetCurrentThreadHandle(void)
0x18007ed20  mov     edi, eax
0x18007ed22  xor     r9d, r9d
0x18007ed25  lea     r8, [rsp+28h+arg_0]
0x18007ed2a  lea     edx, [r9+3]
0x18007ed2e  mov     ecx, eax
0x18007ed30  call    cs:__imp_?IsoLockArtifact@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoLockArtifact(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x18007ed36  test    eax, eax
0x18007ed38  js      short loc_18007ED56
0x18007ed3a  mov     rdx, [rsp+28h+arg_0]
0x18007ed3f  mov     ecx, [rbx+8]
0x18007ed42  cmp     [rdx+30h], ecx
0x18007ed45  jnz     short loc_18007ED4E
0x18007ed47  mov     dword ptr [rdx+30h], 0
0x18007ed4e  mov     ecx, edi
0x18007ed50  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x18007ed56  mov     ecx, [rbx+8]
0x18007ed59  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x18007ed5f  nop
0x18007ed60  mov     rbx, [rsp+28h+arg_8]
0x18007ed65  add     rsp, 20h
0x18007ed69  pop     rdi
0x18007ed6a  retn
```
