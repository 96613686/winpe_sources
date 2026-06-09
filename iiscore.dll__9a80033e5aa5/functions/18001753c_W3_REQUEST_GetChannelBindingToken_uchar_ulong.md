# W3_REQUEST::GetChannelBindingToken(uchar * *,ulong *)

- ea: `0x18001753c`
- end: `0x18001769b`
- name: `?GetChannelBindingToken@W3_REQUEST@@QEAAJPEAPEAEPEAK@Z`
- size: `351`
- prototype: `__int64 __fastcall(W3_REQUEST *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020430`

## callees

- `0x18001753c`
- `0x180035010`

## import_xrefs

- `w3dt!UlAtqReceiveChannelBindingToken` at `0x1800175de`
- `w3dt!UlAtqReceiveChannelBindingToken` at `0x180017682`
- `w3dt!UlAtqReceiveChannelBindingToken` at `0x1800175de`
- `w3dt!UlAtqReceiveChannelBindingToken` at `0x180017682`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::GetChannelBindingToken(W3_REQUEST *this, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v5; // rcx
  unsigned int i; // r9d
  _QWORD *v8; // rcx
  void *v9; // rsi
  struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *v10; // rax
  struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *v11; // rbx
  int v12; // ecx
  struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *v13; // rax
  __int64 v15; // rdx
  unsigned int v16; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  *a3 = 0;
  v5 = *((_QWORD *)this + 5);
  v16 = 0;
  if ( !*(_QWORD *)(v5 + 840) )
    return 0;
  for ( i = 0; i < *(unsigned __int16 *)(v5 + 848); ++i )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v5 + 856) + 16LL * i) == 1 )
    {
      _mm_lfence();
      v15 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 856LL) + 16LL * i + 8);
      *a2 = *(unsigned __int8 **)(v15 + 8);
      *a3 = *(_DWORD *)(v15 + 16);
      return 0;
    }
  }
  v8 = (_QWORD *)*((_QWORD *)this + 14);
  v9 = *(void **)(v8[49] + 9440LL);
  if ( !v9 )
    return 0;
  v10 = (struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *)(*(__int64 (__fastcall **)(_QWORD *, __int64))(*v8 + 144LL))(
                                                      v8,
                                                      224);
  v11 = v10;
  if ( !v10 )
    return 2147942408LL;
  v16 = 224;
  v12 = UlAtqReceiveChannelBindingToken(v9, v10, &v16);
  if ( v12 == -2147024662 )
  {
    v13 = (struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 14)
                                                                                                + 144LL))(
                                                        *((_QWORD *)this + 14),
                                                        v16);
    v11 = v13;
    if ( !v13 )
      return 2147942408LL;
    v12 = UlAtqReceiveChannelBindingToken(v9, v13, &v16);
  }
  if ( v12 >= 0 )
  {
    *a2 = v11->ChannelToken;
    *a3 = v11->ChannelTokenSize;
  }
  else if ( v12 == -2147023728 )
  {
    return 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001753c  mov     [rsp+arg_8], rbx
0x180017541  mov     [rsp+arg_10], rsi
0x180017546  push    rdi
0x180017547  push    r14
0x180017549  push    r15
0x18001754b  sub     rsp, 20h
0x18001754f  mov     qword ptr [rdx], 0
0x180017556  mov     rdi, rcx
0x180017559  mov     dword ptr [r8], 0
0x180017560  mov     r14, r8
0x180017563  mov     rcx, [rcx+28h]
0x180017567  mov     r15, rdx
0x18001756a  mov     [rsp+38h+arg_0], 0
0x180017572  cmp     qword ptr [rcx+348h], 0
0x18001757a  jz      loc_180017673
0x180017580  movzx   r8d, word ptr [rcx+350h]
0x180017588  xor     r9d, r9d
0x18001758b  cmp     r9d, r8d
0x18001758e  jb      loc_180017638
0x180017594  mov     rcx, [rdi+70h]
0x180017598  mov     rax, [rcx+188h]
0x18001759f  mov     rsi, [rax+24E0h]
0x1800175a6  test    rsi, rsi
0x1800175a9  jz      loc_180017673
0x1800175af  mov     rax, [rcx]
0x1800175b2  mov     edx, 0E0h
0x1800175b7  mov     rax, [rax+90h]
0x1800175be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175c3  mov     rbx, rax
0x1800175c6  test    rax, rax
0x1800175c9  jz      short loc_18001760C
0x1800175cb  lea     r8, [rsp+38h+arg_0]
0x1800175d0  mov     [rsp+38h+arg_0], 0E0h
0x1800175d8  mov     rdx, rax
0x1800175db  mov     rcx, rsi
0x1800175de  call    cs:__imp_?UlAtqReceiveChannelBindingToken@@YAJPEAXPEAU_HTTP_REQUEST_CHANNEL_BIND_STATUS@@PEAK@Z; UlAtqReceiveChannelBindingToken(void *,_HTTP_REQUEST_CHANNEL_BIND_STATUS *,ulong *)
0x1800175e4  mov     ecx, eax
0x1800175e6  cmp     eax, 800700EAh
0x1800175eb  jnz     short loc_180017625
0x1800175ed  mov     rcx, [rdi+70h]
0x1800175f1  mov     edx, [rsp+38h+arg_0]
0x1800175f5  mov     rax, [rcx]
0x1800175f8  mov     rax, [rax+90h]
0x1800175ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017604  mov     rbx, rax
0x180017607  test    rax, rax
0x18001760a  jnz     short loc_180017677
0x18001760c  mov     eax, 80070008h
0x180017611  mov     rbx, [rsp+38h+arg_8]
0x180017616  mov     rsi, [rsp+38h+arg_10]
0x18001761b  add     rsp, 20h
0x18001761f  pop     r15
0x180017621  pop     r14
0x180017623  pop     rdi
0x180017624  retn
0x180017625  test    ecx, ecx
0x180017627  jns     short loc_18001768C
0x180017629  xor     eax, eax
0x18001762b  cmp     ecx, 80070490h
0x180017631  cmovz   ecx, eax
0x180017634  mov     eax, ecx
0x180017636  jmp     short loc_180017611
0x180017638  mov     rax, [rcx+358h]
0x18001763f  mov     edx, r9d
0x180017642  add     rdx, rdx
0x180017645  cmp     dword ptr [rax+rdx*8], 1
0x180017649  jz      short loc_180017653
0x18001764b  inc     r9d
0x18001764e  jmp     loc_18001758B
0x180017653  lfence
0x180017656  mov     rax, [rdi+28h]
0x18001765a  mov     rcx, [rax+358h]
0x180017661  mov     rdx, [rcx+rdx*8+8]
0x180017666  mov     rax, [rdx+8]
0x18001766a  mov     [r15], rax
0x18001766d  mov     eax, [rdx+10h]
0x180017670  mov     [r14], eax
0x180017673  xor     eax, eax
0x180017675  jmp     short loc_180017611
0x180017677  lea     r8, [rsp+38h+arg_0]
0x18001767c  mov     rdx, rax
0x18001767f  mov     rcx, rsi
0x180017682  call    cs:__imp_?UlAtqReceiveChannelBindingToken@@YAJPEAXPEAU_HTTP_REQUEST_CHANNEL_BIND_STATUS@@PEAK@Z; UlAtqReceiveChannelBindingToken(void *,_HTTP_REQUEST_CHANNEL_BIND_STATUS *,ulong *)
0x180017688  mov     ecx, eax
0x18001768a  jmp     short loc_180017625
0x18001768c  mov     rax, [rbx+8]
0x180017690  mov     [r15], rax
0x180017693  mov     eax, [rbx+10h]
0x180017696  mov     [r14], eax
0x180017699  jmp     short loc_180017634
```
