# CADMCOMW::InitializeAboWrapper(void)

- ea: `0x18000dafc`
- end: `0x18000dba1`
- name: `?InitializeAboWrapper@CADMCOMW@@SAJXZ`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a0b0`

## callees

- `0x180001064`
- `0x18000dafc`
- `0x180010010`

## import_xrefs

- `abocomp!GetAboWrapper` at `0x18000db4d`
- `abocomp!GetAboWrapper` at `0x18000db4d`
- `abocomp!InitializeAboCompatibilityLayer` at `0x18000db35`
- `abocomp!InitializeAboCompatibilityLayer` at `0x18000db35`
- `abocomp!TerminateAboCompatibilityLayer` at `0x18000db80`
- `abocomp!TerminateAboCompatibilityLayer` at `0x18000db80`

## pseudocode

```c
__int64 CADMCOMW::InitializeAboWrapper(void)
{
  struct IAboSink *v0; // rax
  int v1; // edi
  int AboWrapper; // ebx

  v0 = (struct IAboSink *)g_pAboSink;
  v1 = 0;
  if ( g_pAboSink )
  {
LABEL_4:
    AboWrapper = InitializeAboCompatibilityLayer(v0);
    if ( AboWrapper >= 0 )
    {
      v1 = 1;
      AboWrapper = GetAboWrapper(&CADMCOMW::s_pAboWrapper);
      if ( AboWrapper >= 0 )
        return (unsigned int)AboWrapper;
    }
    goto LABEL_6;
  }
  v0 = (struct IAboSink *)operator new(8u);
  if ( v0 )
  {
    g_pAboSink = v0;
    *(_QWORD *)v0 = &CAboSink::`vftable';
    goto LABEL_4;
  }
  g_pAboSink = 0;
  AboWrapper = -2147024888;
LABEL_6:
  if ( CADMCOMW::s_pAboWrapper )
  {
    (*(void (__fastcall **)(struct IAboWrapper *))(*(_QWORD *)CADMCOMW::s_pAboWrapper + 16LL))(CADMCOMW::s_pAboWrapper);
    CADMCOMW::s_pAboWrapper = 0;
  }
  if ( v1 )
    TerminateAboCompatibilityLayer();
  return (unsigned int)AboWrapper;
}

```

## disassembly

```asm
0x18000dafc  mov     [rsp+arg_0], rbx
0x18000db01  push    rdi
0x18000db02  sub     rsp, 20h
0x18000db06  mov     rax, cs:?g_pAboSink@@3PEAVCAboSink@@EA; CAboSink * g_pAboSink
0x18000db0d  xor     edi, edi
0x18000db0f  test    rax, rax
0x18000db12  jnz     short loc_18000DB32
0x18000db14  lea     ecx, [rdi+8]; Size
0x18000db17  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000db1c  test    rax, rax
0x18000db1f  jz      short loc_18000DB93
0x18000db21  lea     rcx, ??_7CAboSink@@6B@; const CAboSink::`vftable'
0x18000db28  mov     cs:?g_pAboSink@@3PEAVCAboSink@@EA, rax; CAboSink * g_pAboSink
0x18000db2f  mov     [rax], rcx
0x18000db32  mov     rcx, rax
0x18000db35  call    cs:__imp_?InitializeAboCompatibilityLayer@@YAJPEAVIAboSink@@@Z; InitializeAboCompatibilityLayer(IAboSink *)
0x18000db3b  mov     ebx, eax
0x18000db3d  test    eax, eax
0x18000db3f  js      short loc_18000DB59
0x18000db41  lea     rcx, ?s_pAboWrapper@CADMCOMW@@0PEAVIAboWrapper@@EA; IAboWrapper * CADMCOMW::s_pAboWrapper
0x18000db48  mov     edi, 1
0x18000db4d  call    cs:__imp_?GetAboWrapper@@YAJPEAPEAVIAboWrapper@@@Z; GetAboWrapper(IAboWrapper * *)
0x18000db53  mov     ebx, eax
0x18000db55  test    eax, eax
0x18000db57  jns     short loc_18000DB86
0x18000db59  mov     rcx, cs:?s_pAboWrapper@CADMCOMW@@0PEAVIAboWrapper@@EA; IAboWrapper * CADMCOMW::s_pAboWrapper
0x18000db60  test    rcx, rcx
0x18000db63  jz      short loc_18000DB7C
0x18000db65  mov     rax, [rcx]
0x18000db68  mov     rax, [rax+10h]
0x18000db6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db71  mov     cs:?s_pAboWrapper@CADMCOMW@@0PEAVIAboWrapper@@EA, 0; IAboWrapper * CADMCOMW::s_pAboWrapper
0x18000db7c  test    edi, edi
0x18000db7e  jz      short loc_18000DB86
0x18000db80  call    cs:__imp_?TerminateAboCompatibilityLayer@@YAXXZ; TerminateAboCompatibilityLayer(void)
0x18000db86  mov     eax, ebx
0x18000db88  mov     rbx, [rsp+28h+arg_0]
0x18000db8d  add     rsp, 20h
0x18000db91  pop     rdi
0x18000db92  retn
0x18000db93  mov     cs:?g_pAboSink@@3PEAVCAboSink@@EA, rdi; CAboSink * g_pAboSink
0x18000db9a  mov     ebx, 80070008h
0x18000db9f  jmp     short loc_18000DB59
```
