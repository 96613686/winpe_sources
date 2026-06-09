# RtlDebugCompactHeap

- ea: `0x1801206b4`
- end: `0x1801207b5`
- name: `RtlDebugCompactHeap`
- size: `257`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180101190`

## callees

- `0x180047480`
- `0x18006ffa0`
- `0x180070490`
- `0x1800b1fc0`
- `0x1800b2c9c`
- `0x1800b32d4`
- `0x1800ff0c8`
- `0x180101190`
- `0x1801206b4`
- `0x180146ad8`
- `0x18016f020`

## string_xrefs

- `0x180120706`: `RtlCompactHeap`

## pseudocode

```c
__int64 __fastcall RtlDebugCompactHeap(_DWORD *Src, unsigned __int8 a2)
{
  char v5; // si
  __int64 v6; // rbx

  if ( (Src[29] & 0x1000000) != 0 )
    return (unsigned int)((__int64 (*)(void))xmmword_1801C4628)();
  v5 = 0;
  if ( (unsigned __int8)RtlpCheckHeapSignature(Src, "RtlCompactHeap") )
  {
    if ( ((*((_BYTE *)Src + 116) | a2) & 1) == 0 )
    {
      RtlEnterCriticalSection(*((_QWORD *)Src + 44));
      v5 = 1;
    }
    RtlpValidateHeap(Src, 0);
    v6 = RtlCompactHeap(Src);
    RtlpValidateHeapHeaders(Src);
  }
  else
  {
    v6 = 0;
  }
  if ( v5 )
    RtlLeaveCriticalSection(*((_QWORD *)Src + 44));
  return v6;
}

```

## disassembly

```asm
0x1801206b4  mov     [rsp+arg_10], rbx
0x1801206b9  mov     [rsp+arg_18], rsi
0x1801206be  mov     [rsp+arg_0], rcx
0x1801206c3  push    rdi
0x1801206c4  sub     rsp, 30h
0x1801206c8  mov     ebx, edx
0x1801206ca  mov     rdi, rcx
0x1801206cd  test    dword ptr [rcx+74h], 1000000h
0x1801206d4  jz      short loc_1801206F5
0x1801206d6  mov     rax, qword ptr cs:xmmword_1801C4628
0x1801206dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801206e2  mov     eax, eax
0x1801206e4  mov     rbx, [rsp+38h+arg_10]
0x1801206e9  mov     rsi, [rsp+38h+arg_18]
0x1801206ee  add     rsp, 30h
0x1801206f2  pop     rdi
0x1801206f3  retn
0x1801206f5  xor     sil, sil
0x1801206f8  mov     [rsp+38h+var_18], sil
0x1801206fd  mov     [rsp+38h+var_10], 0
0x180120706  lea     rdx, aRtlcompactheap_0; "RtlCompactHeap"
0x18012070d  call    RtlpCheckHeapSignature
0x180120712  test    al, al
0x180120714  jnz     short loc_18012071F
0x180120716  xor     ebx, ebx
0x180120718  mov     [rsp+38h+var_10], rbx
0x18012071d  jmp     short loc_180120772
0x18012071f  mov     eax, [rdi+74h]
0x180120722  bts     eax, 1Ch
0x180120726  or      ebx, eax
0x180120728  mov     [rsp+38h+arg_8], ebx
0x18012072c  test    bl, 1
0x18012072f  jnz     short loc_18012074C
0x180120731  mov     rcx, [rdi+160h]
0x180120738  call    RtlEnterCriticalSection
0x18012073d  mov     sil, 1
0x180120740  mov     [rsp+38h+var_18], sil
0x180120745  or      ebx, 1
0x180120748  mov     [rsp+38h+arg_8], ebx
0x18012074c  xor     edx, edx
0x18012074e  mov     rcx, rdi
0x180120751  call    RtlpValidateHeap
0x180120756  mov     edx, ebx
0x180120758  mov     rcx, rdi
0x18012075b  call    RtlCompactHeap
0x180120760  mov     rbx, rax
0x180120763  mov     [rsp+38h+var_10], rax
0x180120768  mov     dl, 1
0x18012076a  mov     rcx, rdi; Src
0x18012076d  call    RtlpValidateHeapHeaders
0x180120772  jmp     short loc_18012079C
0x180120774  mov     rbx, gs:30h
0x18012077d  mov     [rbx+1250h], eax
0x180120783  mov     ecx, eax
0x180120785  call    RtlNtStatusToDosErrorNoTeb
0x18012078a  mov     [rbx+68h], eax
0x18012078d  mov     rdi, [rsp+38h+arg_0]
0x180120792  mov     sil, [rsp+38h+var_18]
0x180120797  mov     rbx, [rsp+38h+var_10]
0x18012079c  test    sil, sil
0x18012079f  jz      short loc_1801207AD
0x1801207a1  mov     rcx, [rdi+160h]
0x1801207a8  call    RtlLeaveCriticalSection
0x1801207ad  mov     rax, rbx
0x1801207b0  jmp     loc_1801206E4
0x180168ba7  push    rbp
0x180168ba9  sub     rsp, 20h
0x180168bad  mov     rbp, rdx
0x180168bb0  mov     rdx, rcx
0x180168bb3  mov     rcx, [rcx]
0x180168bb6  mov     ecx, [rcx]
0x180168bb8  call    RtlpHeapExceptionFilter
0x180168bbd  nop
0x180168bbe  add     rsp, 20h
0x180168bc2  pop     rbp
0x180168bc3  retn
0x180168bc5  push    rbp
0x180168bc7  sub     rsp, 20h
0x180168bcb  mov     rbp, rdx
0x180168bce  cmp     byte ptr [rbp+20h], 0
0x180168bd2  jz      short loc_180168BE5
0x180168bd4  mov     rcx, [rbp+40h]
0x180168bd8  mov     rcx, [rcx+160h]
0x180168bdf  call    RtlLeaveCriticalSection
0x180168be4  nop
0x180168be5  add     rsp, 20h
0x180168be9  pop     rbp
0x180168bea  retn
```
