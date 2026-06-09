# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x18001db90`
- end: `0x18001dc20`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001dad0`
- `0x18001dc30`
- `0x18001dc40`
- `0x18001dc50`
- `0x18001dc60`

## callees

- `0x18001db90`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 9);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 9, v1 - 1, v1);
    v3 = v1 == v4;
    v1 = v4;
    if ( v3 )
      goto LABEL_10;
  }
  do
    v5 = *(_DWORD *)(2 * v1 + 0x10);
  while ( v5 != 0x7FFFFFFF && v5 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v5 - 1, v5) );
  v2 = v5 - 1;
LABEL_10:
  if ( !v2 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 72))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18001db90  push    rbx
0x18001db92  sub     rsp, 20h
0x18001db96  mov     rdx, [rcx+48h]
0x18001db9a  mov     r9, rcx
0x18001db9d  mov     r10d, 7FFFFFFFh
0x18001dba3  test    rdx, rdx
0x18001dba6  js      short loc_18001DBD7
0x18001dba8  cmp     edx, r10d
0x18001dbab  jz      short loc_18001DBC1
0x18001dbad  lea     rbx, [rdx-1]
0x18001dbb1  mov     rax, rdx
0x18001dbb4  lock cmpxchg [rcx+48h], rbx
0x18001dbba  mov     rdx, rax
0x18001dbbd  jnz     short loc_18001DBA3
0x18001dbbf  jmp     short loc_18001DBE5
0x18001dbc1  mov     ebx, 7FFFFFFEh
0x18001dbc6  jmp     short loc_18001DC18
0x18001dbc8  lea     ecx, [r8-1]
0x18001dbcc  mov     eax, r8d
0x18001dbcf  lock cmpxchg [rdx+rdx+10h], ecx
0x18001dbd5  jz      short loc_18001DBE1
0x18001dbd7  mov     r8d, [rdx+rdx+10h]
0x18001dbdc  cmp     r8d, r10d
0x18001dbdf  jnz     short loc_18001DBC8
0x18001dbe1  lea     ebx, [r8-1]
0x18001dbe5  test    ebx, ebx
0x18001dbe7  jnz     short loc_18001DC18
0x18001dbe9  test    r9, r9
0x18001dbec  jz      short loc_18001DC00
0x18001dbee  mov     rax, [r9]
0x18001dbf1  lea     edx, [rbx+1]
0x18001dbf4  mov     rcx, r9
0x18001dbf7  mov     rax, [rax+48h]
0x18001dbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc00  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001dc07  test    rcx, rcx
0x18001dc0a  jz      short loc_18001DC18
0x18001dc0c  mov     rdx, [rcx]
0x18001dc0f  mov     rax, [rdx+10h]
0x18001dc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc18  mov     eax, ebx
0x18001dc1a  add     rsp, 20h
0x18001dc1e  pop     rbx
0x18001dc1f  retn
```
