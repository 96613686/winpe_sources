# InitDebugRpcFlag

- ea: `0x180013a74`
- end: `0x180013b12`
- name: `InitDebugRpcFlag`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013b18`

## callees

- `0x1800049ac`
- `0x180013a74`
- `0x18001786c`

## string_xrefs

- `0x180013a83`: `security`

## pseudocode

```c
char InitDebugRpcFlag()
{
  char result; // al
  int v1; // [rsp+20h] [rbp-38h] BYREF
  const wchar_t *v2; // [rsp+28h] [rbp-30h]
  const wchar_t *v3; // [rsp+30h] [rbp-28h]
  int v4; // [rsp+38h] [rbp-20h]
  __int64 v5; // [rsp+40h] [rbp-18h]

  v1 = 0;
  v2 = L"security";
  v3 = L"DebugRpc";
  v4 = 0;
  v5 = 0;
  QueryValueInternal((struct RegEntry *)&v1);
  result = 0;
  g_fDebugRpc = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0 )
    return WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 11, WPP_a622e3c3ed763f2fd36243d1ce35f31d_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x180013a74  mov     r11, rsp
0x180013a77  sub     rsp, 58h
0x180013a7b  mov     [rsp+58h+var_38], 0
0x180013a83  lea     rax, aSecurity; "security"
0x180013a8a  mov     [r11-30h], rax
0x180013a8e  lea     r8, [r11+8]
0x180013a92  lea     rax, aDebugrpc; "DebugRpc"
0x180013a99  mov     [rsp+58h+arg_0], 0
0x180013aa1  mov     r9d, 4
0x180013aa7  mov     [r11-28h], rax
0x180013aab  mov     [rsp+58h+var_20], 0
0x180013ab3  lea     rcx, [r11-38h]; struct RegEntry *
0x180013ab7  mov     edx, r9d
0x180013aba  mov     qword ptr [r11-18h], 0
0x180013ac2  call    QueryValueInternal
0x180013ac7  cmp     [rsp+58h+arg_0], 0
0x180013acc  setnz   al
0x180013acf  mov     cs:?g_fDebugRpc@@3_NA, al; bool g_fDebugRpc
0x180013ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180013adc  lea     rdx, WPP_GLOBAL_Control
0x180013ae3  cmp     rcx, rdx
0x180013ae6  jz      short loc_180013B0D
0x180013ae8  test    byte ptr [rcx+0BCh], 4
0x180013aef  jz      short loc_180013B0D
0x180013af1  mov     rcx, [rcx+0B0h]
0x180013af8  lea     r8, WPP_a622e3c3ed763f2fd36243d1ce35f31d_Traceguids
0x180013aff  movzx   r9d, al
0x180013b03  mov     edx, 0Bh
0x180013b08  call    WPP_SF_d
0x180013b0d  add     rsp, 58h
0x180013b11  retn
```
