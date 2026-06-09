# CVolumeCacheCallBack::ScanProgress(unsigned __int64,ulong,ushort const *)

- ea: `0x140005a70`
- end: `0x140005aab`
- name: `?ScanProgress@CVolumeCacheCallBack@@UEAAJ_KKPEBG@Z`
- size: `59`
- prototype: `__int64 __fastcall(CVolumeCacheCallBack *this, __int64, char, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005a70`

## pseudocode

```c
__int64 __fastcall CVolumeCacheCallBack::ScanProgress(
        CVolumeCacheCallBack *this,
        __int64 a2,
        char a3,
        const unsigned __int16 *a4)
{
  if ( qword_140021678 )
    *(_QWORD *)(qword_140021678 + 592) = a2;
  if ( (a3 & 1) != 0 )
    qword_140021678 = 0;
  return *(_DWORD *)(qword_140021680 + 1768) != 0 ? 0x80004004 : 0;
}

```

## disassembly

```asm
0x140005a70  mov     rax, cs:qword_140021678
0x140005a77  test    rax, rax
0x140005a7a  jz      short loc_140005A83
0x140005a7c  mov     [rax+250h], rdx
0x140005a83  test    r8b, 1
0x140005a87  jz      short loc_140005A94
0x140005a89  mov     cs:qword_140021678, 0
0x140005a94  mov     rax, cs:qword_140021680
0x140005a9b  mov     ecx, [rax+6E8h]
0x140005aa1  neg     ecx
0x140005aa3  sbb     eax, eax
0x140005aa5  and     eax, 80004004h
0x140005aaa  retn
```
