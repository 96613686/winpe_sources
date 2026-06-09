# RemoveUnreferencedDevices

- ea: `0x180063458`
- end: `0x180063559`
- name: `RemoveUnreferencedDevices`
- size: `257`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006338c`

## callees

- `0x180036030`
- `0x180063458`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1800634bf`
- `ntoskrnl!IofCompleteRequest` at `0x1800634bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800634df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800634fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063530`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800634df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800634fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063530`

## pseudocode

```c
void __fastcall RemoveUnreferencedDevices(_QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v3; // rbp
  _QWORD **v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  IRP *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rax
  _QWORD *v11; // rcx

  v1 = (_QWORD *)*a1;
  if ( (_QWORD *)*a1 != a1 )
  {
    do
    {
      v3 = (_QWORD *)*v1;
      if ( !*((_BYTE *)v1 + 60) )
      {
        RemoveDeviceAssociations((UNICODE_STRING *)v1);
        v4 = (_QWORD **)(v1 + 4);
        while ( 1 )
        {
          v5 = *v4;
          if ( *v4 == v4 )
            break;
          if ( (_QWORD **)v5[1] != v4 )
            goto LABEL_18;
          v6 = (_QWORD *)*v5;
          if ( *(_QWORD **)(*v5 + 8LL) != v5 )
            goto LABEL_18;
          *v4 = v6;
          v7 = (IRP *)(v5 - 21);
          v6[1] = v4;
          v7->IoStatus.Status = -1073741772;
          IofCompleteRequest(v7, 0);
        }
        if ( !v1[6] )
        {
          v8 = (void *)v1[12];
          if ( v8 )
          {
            ExFreePoolWithTag(v8, 0);
            v1[12] = 0;
          }
          v9 = (void *)v1[13];
          if ( v9 )
          {
            ExFreePoolWithTag(v9, 0);
            v1[13] = 0;
          }
          v10 = *v1;
          if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v11 = (_QWORD *)v1[1], (_QWORD *)*v11 != v1) )
LABEL_18:
            __fastfail(3u);
          *v11 = v10;
          *(_QWORD *)(v10 + 8) = v11;
          ExFreePoolWithTag(v1, 0);
        }
      }
      v1 = v3;
    }
    while ( v3 != a1 );
  }
}

```

## disassembly

```asm
0x180063458  push    rbx
0x18006345a  push    rbp
0x18006345b  push    rsi
0x18006345c  push    rdi
0x18006345d  sub     rsp, 28h
0x180063461  mov     rbx, [rcx]
0x180063464  mov     rsi, rcx
0x180063467  cmp     rbx, rcx
0x18006346a  jz      loc_180063548
0x180063470  cmp     byte ptr [rbx+3Ch], 0
0x180063474  mov     rbp, [rbx]
0x180063477  jnz     loc_18006353C
0x18006347d  mov     rcx, rbx
0x180063480  call    RemoveDeviceAssociations
0x180063485  lea     rdi, [rbx+20h]
0x180063489  mov     rcx, [rdi]
0x18006348c  cmp     rcx, rdi
0x18006348f  jz      short loc_1800634CD
0x180063491  cmp     [rcx+8], rdi
0x180063495  jnz     loc_180063552
0x18006349b  mov     rax, [rcx]
0x18006349e  cmp     [rax+8], rcx
0x1800634a2  jnz     loc_180063552
0x1800634a8  mov     [rdi], rax
0x1800634ab  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1800634b2  mov     [rax+8], rdi
0x1800634b6  xor     edx, edx; PriorityBoost
0x1800634b8  mov     dword ptr [rcx+30h], 0C0000034h
0x1800634bf  call    cs:__imp_IofCompleteRequest
0x1800634c6  nop     dword ptr [rax+rax+00h]
0x1800634cb  jmp     short loc_180063489
0x1800634cd  cmp     qword ptr [rbx+30h], 0
0x1800634d2  jnz     short loc_18006353C
0x1800634d4  mov     rcx, [rbx+60h]; P
0x1800634d8  test    rcx, rcx
0x1800634db  jz      short loc_1800634F3
0x1800634dd  xor     edx, edx; Tag
0x1800634df  call    cs:__imp_ExFreePoolWithTag
0x1800634e6  nop     dword ptr [rax+rax+00h]
0x1800634eb  mov     qword ptr [rbx+60h], 0
0x1800634f3  mov     rcx, [rbx+68h]; P
0x1800634f7  test    rcx, rcx
0x1800634fa  jz      short loc_180063512
0x1800634fc  xor     edx, edx; Tag
0x1800634fe  call    cs:__imp_ExFreePoolWithTag
0x180063505  nop     dword ptr [rax+rax+00h]
0x18006350a  mov     qword ptr [rbx+68h], 0
0x180063512  mov     rax, [rbx]
0x180063515  cmp     [rax+8], rbx
0x180063519  jnz     short loc_180063552
0x18006351b  mov     rcx, [rbx+8]
0x18006351f  cmp     [rcx], rbx
0x180063522  jnz     short loc_180063552
0x180063524  mov     [rcx], rax
0x180063527  xor     edx, edx; Tag
0x180063529  mov     [rax+8], rcx
0x18006352d  mov     rcx, rbx; P
0x180063530  call    cs:__imp_ExFreePoolWithTag
0x180063537  nop     dword ptr [rax+rax+00h]
0x18006353c  mov     rbx, rbp
0x18006353f  cmp     rbp, rsi
0x180063542  jnz     loc_180063470
0x180063548  add     rsp, 28h
0x18006354c  pop     rdi
0x18006354d  pop     rsi
0x18006354e  pop     rbp
0x18006354f  pop     rbx
0x180063550  retn
0x180063552  mov     ecx, 3
0x180063557  int     29h; Win8: RtlFailFast(ecx)
```
