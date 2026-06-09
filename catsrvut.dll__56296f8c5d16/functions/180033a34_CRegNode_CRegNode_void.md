# CRegNode::~CRegNode(void)

- ea: `0x180033a34`
- end: `0x180033ae8`
- name: `??1CRegNode@@QEAA@XZ`
- size: `180`
- prototype: `void __fastcall(CRegNode *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003387c`

## callees

- `0x180033a08`
- `0x180033a34`
- `0x1800341cc`
- `0x180034f88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033aa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033aa1`

## pseudocode

```c
void __fastcall CRegNode::~CRegNode(CRegNode *this)
{
  void *v2; // rdi
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = 0;
  if ( *((_QWORD *)this + 9) )
  {
    CRegNode::FlushHkeyMap(this, 1u);
    v2 = (void *)*((_QWORD *)this + 9);
    if ( v2 )
    {
      CHkeyCache::~CHkeyCache(*((void ***)this + 9));
      CoTaskMemFree(v2);
    }
    *((_QWORD *)this + 9) = 0;
  }
  else
  {
    RegSafeCloseKey(*((HKEY *)this + 3));
  }
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 4) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 6);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 6) = 0;
  }
  RegSafeCloseKey(*((HKEY *)this + 2));
  *((_DWORD *)this + 2) &= 0xFFFFFFFC;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 131097;
}

```

## disassembly

```asm
0x180033a34  mov     [rsp+arg_0], rbx
0x180033a39  mov     [rsp+arg_8], rsi
0x180033a3e  push    rdi
0x180033a3f  sub     rsp, 20h
0x180033a43  mov     rbx, rcx
0x180033a46  xor     esi, esi
0x180033a48  mov     [rcx], rsi
0x180033a4b  cmp     [rcx+48h], rsi
0x180033a4f  jz      short loc_180033A7B
0x180033a51  lea     edx, [rsi+1]; unsigned int
0x180033a54  call    ?FlushHkeyMap@CRegNode@@AEAAXK@Z; CRegNode::FlushHkeyMap(ulong)
0x180033a59  mov     rdi, [rbx+48h]
0x180033a5d  test    rdi, rdi
0x180033a60  jz      short loc_180033A75
0x180033a62  mov     rcx, rdi; this
0x180033a65  call    ??1CHkeyCache@@QEAA@XZ; CHkeyCache::~CHkeyCache(void)
0x180033a6a  nop
0x180033a6b  mov     rcx, rdi; pv
0x180033a6e  call    cs:__imp_CoTaskMemFree
0x180033a74  nop
0x180033a75  mov     [rbx+48h], rsi
0x180033a79  jmp     short loc_180033A84
0x180033a7b  mov     rcx, [rcx+18h]; HKEY
0x180033a7f  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180033a84  mov     rcx, [rbx+20h]; pv
0x180033a88  test    rcx, rcx
0x180033a8b  jz      short loc_180033A98
0x180033a8d  call    cs:__imp_CoTaskMemFree
0x180033a93  nop
0x180033a94  mov     [rbx+20h], rsi
0x180033a98  mov     rcx, [rbx+30h]; pv
0x180033a9c  test    rcx, rcx
0x180033a9f  jz      short loc_180033AAC
0x180033aa1  call    cs:__imp_CoTaskMemFree
0x180033aa7  nop
0x180033aa8  mov     [rbx+30h], rsi
0x180033aac  mov     rcx, [rbx+10h]; HKEY
0x180033ab0  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180033ab5  and     dword ptr [rbx+8], 0FFFFFFFCh
0x180033ab9  mov     [rbx+10h], rsi
0x180033abd  mov     [rbx+18h], rsi
0x180033ac1  mov     [rbx+20h], rsi
0x180033ac5  mov     [rbx+28h], rsi
0x180033ac9  mov     [rbx+30h], rsi
0x180033acd  mov     [rbx+38h], rsi
0x180033ad1  mov     dword ptr [rbx+40h], 20019h
0x180033ad8  mov     rbx, [rsp+28h+arg_0]
0x180033add  mov     rsi, [rsp+28h+arg_8]
0x180033ae2  add     rsp, 20h
0x180033ae6  pop     rdi
0x180033ae7  retn
```
