# _ApplySecurityToRegistryTree(HKEY__ *,void *,void *,int,int)

- ea: `0x180012388`
- end: `0x1800123a6`
- name: `?_ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEAX1HH@Z`
- size: `30`
- prototype: `__int64 __fastcall(HKEY, void *, void *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800121fc`

## callees

- `0x18000e640`

## pseudocode

```c
__int64 __fastcall _ApplySecurityToRegistryTree(HKEY a1, void *a2, void *a3, int a4, int a5)
{
  return _ApplySecurityToRegistryTreeEx(a1, a2, a3, a4, a5, 0);
}

```

## disassembly

```asm
0x180012388  sub     rsp, 38h
0x18001238c  mov     eax, [rsp+38h+arg_20]
0x180012390  mov     [rsp+38h+cbMaxSubKeyLen], 0; cbMaxSubKeyLen
0x180012398  mov     [rsp+38h+var_18], eax; int
0x18001239c  call    ?_ApplySecurityToRegistryTreeEx@@YAJPEAUHKEY__@@PEAX1HHH@Z; _ApplySecurityToRegistryTreeEx(HKEY__ *,void *,void *,int,int,int)
0x1800123a1  add     rsp, 38h
0x1800123a5  retn
```
