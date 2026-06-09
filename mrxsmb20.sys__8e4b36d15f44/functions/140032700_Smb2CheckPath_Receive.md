# Smb2CheckPath_Receive

- ea: `0x140032700`
- end: `0x140032893`
- name: `Smb2CheckPath_Receive`
- size: `403`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140015570`
- `0x140032700`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140032814`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140032814`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140032749`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14003287b`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140032749`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14003287b`

## pseudocode

```c
__int64 __fastcall Smb2CheckPath_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7)
{
  int v7; // edi
  __int64 v8; // rbx
  __int64 v12; // rdx

  v7 = *(_DWORD *)(a3 + 16);
  v8 = a1;
  LOBYTE(a1) = *(_BYTE *)(a1 + 3800);
  if ( (_BYTE)a1 && a2 == v8 + 1024 && v7 == -2147483603 )
  {
    SmbCseUpdateBufferContextStatus(a2, 0xF8000002DLL);
    return Smb2BufferErrorResponse(a2, a7, a4, a5, a6);
  }
  if ( v7 < 0 || (_BYTE)a1 || a2 != v8 + 1024 )
    goto LABEL_14;
  if ( a4 >= 0x7C )
  {
    v12 = *(_QWORD *)(v8 + 3808);
    if ( !v12 )
      goto LABEL_16;
    if ( *(_DWORD *)(v8 + 3816) < 0x38u )
    {
      v7 = -1073741789;
      goto LABEL_16;
    }
    a1 = a7;
    *(_QWORD *)(v12 + 32) = *(_QWORD *)(a7 + 104);
    *(_QWORD *)(v12 + 24) = *(_QWORD *)(a7 + 96);
    *(_QWORD *)v12 = *(_QWORD *)(a7 + 72);
    *(_QWORD *)(v12 + 40) = *(_QWORD *)(a7 + 112);
    *(_DWORD *)(v12 + 48) = *(_DWORD *)(a7 + 120);
    *(_QWORD *)(v12 + 8) = *(_QWORD *)(a7 + 80);
    *(_QWORD *)(v12 + 16) = *(_QWORD *)(a7 + 88);
    *(_DWORD *)(v8 + 3816) -= 56;
LABEL_14:
    if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 64) & 1) != 0 )
      _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                      * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                     % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 88)
                                                                                             + 424LL)
                                                                                 + 1488LL))
                                                      + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 88) + 424LL) + 1480LL)
                                                      + 84));
    goto LABEL_16;
  }
  v7 = -1073741629;
LABEL_16:
  *a6 = a5;
  SmbCseUpdateBufferContextStatus(a2, (unsigned int)v7);
  return 0;
}

```

## disassembly

```asm
0x140032700  push    rbx
0x140032702  push    rbp
0x140032703  push    rsi
0x140032704  push    rdi
0x140032705  sub     rsp, 38h
0x140032709  mov     edi, [r8+10h]
0x14003270d  mov     rbx, rcx
0x140032710  mov     cl, [rcx+0ED8h]
0x140032716  mov     ebp, r9d
0x140032719  mov     rsi, rdx
0x14003271c  test    cl, cl
0x14003271e  jz      short loc_140032782
0x140032720  lea     rax, [rbx+400h]
0x140032727  cmp     rdx, rax
0x14003272a  jnz     short loc_140032782
0x14003272c  mov     eax, 8000002Dh
0x140032731  cmp     edi, eax
0x140032733  jnz     short loc_140032782
0x140032735  mov     dword ptr [rsp+58h+arg_0], eax
0x140032739  mov     rcx, rsi
0x14003273c  mov     dword ptr [rsp+58h+arg_0+4], 0Fh
0x140032744  mov     rdx, [rsp+58h+arg_0]
0x140032749  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x140032750  nop     dword ptr [rax+rax+00h]
0x140032755  mov     rax, [rsp+58h+arg_28]
0x14003275d  mov     r8d, ebp
0x140032760  mov     r9d, [rsp+58h+arg_20]
0x140032768  mov     rcx, rsi
0x14003276b  mov     rdx, [rsp+58h+arg_30]
0x140032773  mov     [rsp+58h+var_38], rax
0x140032778  call    Smb2BufferErrorResponse
0x14003277d  jmp     loc_140032889
0x140032782  test    edi, edi
0x140032784  js      loc_140032814
0x14003278a  test    cl, cl
0x14003278c  jnz     loc_140032814
0x140032792  lea     rax, [rbx+400h]
0x140032799  cmp     rsi, rax
0x14003279c  jnz     short loc_140032814
0x14003279e  cmp     ebp, 7Ch ; '|'
0x1400327a1  jnb     short loc_1400327AD
0x1400327a3  mov     edi, 0C00000C3h
0x1400327a8  jmp     loc_140032856
0x1400327ad  mov     rdx, [rbx+0EE0h]
0x1400327b4  test    rdx, rdx
0x1400327b7  jz      loc_140032856
0x1400327bd  cmp     dword ptr [rbx+0EE8h], 38h ; '8'
0x1400327c4  jnb     short loc_1400327D0
0x1400327c6  mov     edi, 0C0000023h
0x1400327cb  jmp     loc_140032856
0x1400327d0  mov     rcx, [rsp+58h+arg_30]
0x1400327d8  mov     rax, [rcx+68h]
0x1400327dc  mov     [rdx+20h], rax
0x1400327e0  mov     rax, [rcx+60h]
0x1400327e4  mov     [rdx+18h], rax
0x1400327e8  mov     rax, [rcx+48h]
0x1400327ec  mov     [rdx], rax
0x1400327ef  mov     rax, [rcx+70h]
0x1400327f3  mov     [rdx+28h], rax
0x1400327f7  mov     eax, [rcx+78h]
0x1400327fa  mov     [rdx+30h], eax
0x1400327fd  mov     rax, [rcx+50h]
0x140032801  mov     [rdx+8], rax
0x140032805  mov     rax, [rcx+58h]
0x140032809  mov     [rdx+10h], rax
0x14003280d  add     dword ptr [rbx+0EE8h], 0FFFFFFC8h
0x140032814  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14003281b  nop     dword ptr [rax+rax+00h]
0x140032820  test    byte ptr [rax+40h], 1
0x140032824  jz      short loc_140032856
0x140032826  mov     rax, [rbx+58h]
0x14003282a  xor     edx, edx
0x14003282c  mov     r8, [rax+1A8h]
0x140032833  mov     eax, gs:1A4h
0x14003283b  div     dword ptr [r8+5D0h]
0x140032842  mov     rax, [r8+5C8h]
0x140032849  lea     rdx, [rdx+rdx*2]
0x14003284d  shl     rdx, 6
0x140032851  lock inc dword ptr [rdx+rax+54h]
0x140032856  mov     rcx, [rsp+58h+arg_28]
0x14003285e  mov     eax, [rsp+58h+arg_20]
0x140032865  mov     dword ptr [rsp+58h+arg_0], edi
0x140032869  mov     dword ptr [rsp+58h+arg_0+4], 0
0x140032871  mov     rdx, [rsp+58h+arg_0]
0x140032876  mov     [rcx], eax
0x140032878  mov     rcx, rsi
0x14003287b  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x140032882  nop     dword ptr [rax+rax+00h]
0x140032887  xor     eax, eax
0x140032889  add     rsp, 38h
0x14003288d  pop     rdi
0x14003288e  pop     rsi
0x14003288f  pop     rbp
0x140032890  pop     rbx
0x140032891  retn
```
