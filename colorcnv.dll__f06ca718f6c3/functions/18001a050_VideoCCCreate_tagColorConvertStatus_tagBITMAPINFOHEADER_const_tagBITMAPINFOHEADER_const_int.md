# VideoCCCreate(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,int)

- ea: `0x18001a050`
- end: `0x18001a05e`
- name: `?VideoCCCreate@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1H@Z`
- size: `14`
- prototype: `void *__fastcall(enum tagColorConvertStatus *, const struct tagBITMAPINFOHEADER *, const struct tagBITMAPINFOHEADER *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001a064`

## pseudocode

```c
_QWORD *__fastcall VideoCCCreate(
        enum tagColorConvertStatus *a1,
        const struct tagBITMAPINFOHEADER *a2,
        const struct tagBITMAPINFOHEADER *a3,
        int a4)
{
  return VideoNewCCCreate(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a050  sub     rsp, 38h
0x18001a054  call    ?VideoNewCCCreate@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1HJ@Z; VideoNewCCCreate(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,int,long)
0x18001a059  add     rsp, 38h
0x18001a05d  retn
```
