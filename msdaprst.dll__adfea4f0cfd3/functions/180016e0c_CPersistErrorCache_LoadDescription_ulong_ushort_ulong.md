# CPersistErrorCache::LoadDescription(ulong,ushort *,ulong)

- ea: `0x180016e0c`
- end: `0x180016ea3`
- name: `?LoadDescription@CPersistErrorCache@@AEAAXKPEAGK@Z`
- size: `151`
- prototype: `void(CPersistErrorCache *__hidden this, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180016764`

## callees

- `0x18000ca88`
- `0x180016e0c`
- `0x180016eac`
- `0x18002f0aa`

## import_xrefs

- `USER32!LoadStringW` at `0x180016e63`
- `USER32!LoadStringW` at `0x180016e63`

## string_xrefs

- `0x180016e77`: `Can not load msdaprsr.dll.`

## pseudocode

```c
void __fastcall CPersistErrorCache::LoadDescription(CPersistErrorCache *this, UINT a2, unsigned __int16 *a3)
{
  HINSTANCE v3; // rbx

  v3 = g_hinstance_PersistR;
  if ( (g_hinstance_PersistR || (LoadPersistR(), (v3 = g_hinstance_PersistR) != 0)) && a2 != 137 )
  {
    memset_0(a3, 0, 0x400u);
    LoadStringW(v3, a2, a3, 1024);
  }
  else
  {
    StringCchCopyNW(a3, 0x400u, L"Can not load msdaprsr.dll.", 0x400u);
    a3[1023] = 0;
  }
}

```

## disassembly

```asm
0x180016e0c  mov     [rsp+arg_0], rbx
0x180016e11  mov     [rsp+arg_8], rbp
0x180016e16  push    rsi
0x180016e17  sub     rsp, 20h
0x180016e1b  mov     rbx, cs:?g_hinstance_PersistR@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance_PersistR
0x180016e22  mov     rsi, r8
0x180016e25  mov     ebp, edx
0x180016e27  test    rbx, rbx
0x180016e2a  jnz     short loc_180016E3D
0x180016e2c  call    ?LoadPersistR@@YAXXZ; LoadPersistR(void)
0x180016e31  mov     rbx, cs:?g_hinstance_PersistR@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstance_PersistR
0x180016e38  test    rbx, rbx
0x180016e3b  jz      short loc_180016E71
0x180016e3d  cmp     ebp, 89h
0x180016e43  jz      short loc_180016E71
0x180016e45  xor     edx, edx; Val
0x180016e47  mov     r8d, 400h; Size
0x180016e4d  mov     rcx, rsi; void *
0x180016e50  call    memset_0
0x180016e55  mov     r9d, 400h; cchBufferMax
0x180016e5b  mov     r8, rsi; lpBuffer
0x180016e5e  mov     edx, ebp; uID
0x180016e60  mov     rcx, rbx; hInstance
0x180016e63  call    cs:__imp_LoadStringW
0x180016e6a  nop     dword ptr [rax+rax+00h]
0x180016e6f  jmp     short loc_180016E92
0x180016e71  mov     r9d, 400h; unsigned __int64
0x180016e77  lea     r8, aCanNotLoadMsda; "Can not load msdaprsr.dll."
0x180016e7e  mov     edx, r9d; unsigned __int64
0x180016e81  mov     rcx, rsi; unsigned __int16 *
0x180016e84  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180016e89  xor     eax, eax
0x180016e8b  mov     [rsi+7FEh], ax
0x180016e92  mov     rbx, [rsp+28h+arg_0]
0x180016e97  mov     rbp, [rsp+28h+arg_8]
0x180016e9c  add     rsp, 20h
0x180016ea0  pop     rsi
0x180016ea1  retn
```
