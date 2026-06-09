# OncRpcMapRpcStatusToNtStatus

- ea: `0x140022220`
- end: `0x140022268`
- name: `OncRpcMapRpcStatusToNtStatus`
- size: `72`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x1400029d0`
- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x1400132cc`
- `0x140020fa8`
- `0x1400219e8`
- `0x14002372c`
- `0x140023dd0`
- `0x14002a5f0`
- `0x14002a9e0`
- `0x14002b138`

## callees

- `0x140022220`
- `0x140022270`

## pseudocode

```c
__int64 __fastcall OncRpcMapRpcStatusToNtStatus(_DWORD *a1)
{
  int v1; // edx
  int v3; // ecx

  v1 = a1[68];
  if ( !v1 )
    return OncRpcpMapRpcAcceptedStatusToNtStatus((unsigned int)a1[160]);
  if ( v1 != 1 )
    return 3221225473LL;
  v3 = a1[72];
  if ( !v3 )
    return 3221225668LL;
  if ( v3 != 1 )
    return 3221225473LL;
  return 3221225506LL;
}

```

## disassembly

```asm
0x140022220  sub     rsp, 28h
0x140022224  mov     edx, [rcx+110h]
0x14002222a  test    edx, edx
0x14002222c  jz      short loc_140022257
0x14002222e  cmp     edx, 1
0x140022231  jz      short loc_14002223A
0x140022233  mov     eax, 0C0000001h
0x140022238  jmp     short loc_140022262
0x14002223a  mov     ecx, [rcx+120h]
0x140022240  test    ecx, ecx
0x140022242  jz      short loc_140022250
0x140022244  cmp     ecx, 1
0x140022247  jnz     short loc_140022233
0x140022249  mov     eax, 0C0000022h
0x14002224e  jmp     short loc_140022262
0x140022250  mov     eax, 0C00000C4h
0x140022255  jmp     short loc_140022262
0x140022257  mov     ecx, [rcx+280h]
0x14002225d  call    OncRpcpMapRpcAcceptedStatusToNtStatus
0x140022262  add     rsp, 28h
0x140022266  retn
```
