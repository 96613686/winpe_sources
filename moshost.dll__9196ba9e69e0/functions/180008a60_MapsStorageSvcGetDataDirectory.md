# MapsStorageSvcGetDataDirectory

- ea: `0x180008a60`
- end: `0x180008aba`
- name: `MapsStorageSvcGetDataDirectory`
- size: `90`
- prototype: `int __fastcall(__int64, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008a60`

## import_xrefs

- `MosStorage!MosStorageGetDataDirectory` at `0x180008a8f`
- `MosStorage!MosStorageGetDataDirectory` at `0x180008a8f`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008a82`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008aac`

## string_xrefs

- `0x180008a72`: `MapsStorageSvcGetDataDirectory`
- `0x180008a9f`: `MapsStorageSvcGetDataDirectory`

## pseudocode

```c
int __fastcall MapsStorageSvcGetDataDirectory(__int64 a1, unsigned __int16 *a2, unsigned int a3)
{
  int DataDirectory; // eax

  if ( !a2 )
    return ZTraceReportOriginationNoThis(-2147467261, "MapsStorageSvcGetDataDirectory", 203);
  DataDirectory = MosStorageGetDataDirectory(a2, a3);
  if ( DataDirectory >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(DataDirectory, "MapsStorageSvcGetDataDirectory", 205);
}

```

## disassembly

```asm
0x180008a60  sub     rsp, 28h
0x180008a64  mov     rax, rdx
0x180008a67  test    rdx, rdx
0x180008a6a  jnz     short loc_180008A89
0x180008a6c  mov     r8d, 0CBh
0x180008a72  lea     rdx, aMapsstoragesvc_3; "MapsStorageSvcGetDataDirectory"
0x180008a79  mov     ecx, 80004003h
0x180008a7e  add     rsp, 28h
0x180008a82  jmp     cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008a89  mov     edx, r8d
0x180008a8c  mov     rcx, rax
0x180008a8f  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x180008a95  test    eax, eax
0x180008a97  jns     short loc_180008AB3
0x180008a99  mov     r8d, 0CDh
0x180008a9f  lea     rdx, aMapsstoragesvc_3; "MapsStorageSvcGetDataDirectory"
0x180008aa6  mov     ecx, eax
0x180008aa8  add     rsp, 28h
0x180008aac  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008ab3  xor     eax, eax
0x180008ab5  add     rsp, 28h
0x180008ab9  retn
```
