# SplitPath(x,x,x,x,x,x,x,x,x)

- ea: `0x1000c2f0`
- end: `0x1000c31f`
- name: `_SplitPath@36`
- size: `47`
- prototype: `int __stdcall(wchar_t *FullPath, wchar_t *Drive, size_t DriveCount, wchar_t *Dir, size_t DirCount, wchar_t *Filename, size_t FilenameCount, wchar_t *Ext, size_t ExtCount)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1000a470`
- `0x1000c370`
- `0x1000cbf0`
- `0x1000d020`
- `0x1000d8d0`
- `0x1000db20`
- `0x1000dfa0`
- `0x1000e3b0`
- `0x1000e950`
- `0x10010450`
- `0x100108e0`
- `0x10010f00`
- `0x10011d90`
- `0x1001ca70`
- `0x1001e1e0`

## callees

- `0x1002c520`

## pseudocode

```c
errno_t __stdcall SplitPath(
        wchar_t *FullPath,
        wchar_t *Drive,
        size_t DriveCount,
        wchar_t *Dir,
        size_t DirCount,
        wchar_t *Filename,
        size_t FilenameCount,
        wchar_t *Ext,
        size_t ExtCount)
{
  return _wsplitpath_s(FullPath, Drive, DriveCount, Dir, DirCount, Filename, FilenameCount, Ext, ExtCount);
}

```

## disassembly

```asm
0x1000c2f0  push    [esp+ExtCount]; ExtCount
0x1000c2f4  push    [esp+4+Ext]; Ext
0x1000c2f8  push    [esp+8+FilenameCount]; FilenameCount
0x1000c2fc  push    [esp+0Ch+Filename]; Filename
0x1000c300  push    [esp+10h+DirCount]; DirCount
0x1000c304  push    [esp+14h+Dir]; Dir
0x1000c308  push    [esp+18h+DriveCount]; DriveCount
0x1000c30c  push    [esp+1Ch+Drive]; Drive
0x1000c310  push    [esp+20h+FullPath]; FullPath
0x1000c314  call    __wsplitpath_s
0x1000c319  add     esp, 24h
0x1000c31c  retn    24h ; '$'
```
