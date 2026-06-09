# RemoveUnreferencedDevices

- ea: `0x1800632b8`
- end: `0x1800633b9`
- name: `RemoveUnreferencedDevices`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800631ec`

## callees

- `0x180035f20`
- `0x1800632b8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18006331f`
- `ntoskrnl!IofCompleteRequest` at `0x18006331f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006333f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006335e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063390`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006333f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006335e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063390`

## pseudocode

```c
void __fastcall RemoveUnreferencedDevices(_QWORD **a1)
{
  _QWORD *v1; // rbx
  _QWORD *v3; // rbp
  _QWORD **v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  IRP *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rcx

  v1 = *a1;
  if ( *a1 != a1 )
  {
    do
    {
      v3 = (_QWORD *)*v1;
      if ( !*((_BYTE *)v1 + 60) )
      {
        RemoveDeviceAssociations(v1);
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
          v10 = (_QWORD *)*v1;
          if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v11 = (_QWORD *)v1[1], (_QWORD *)*v11 != v1) )
LABEL_18:
            __fastfail(3u);
          *v11 = v10;
          v10[1] = v11;
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
0x1800632b8  push    rbx
0x1800632ba  push    rbp
0x1800632bb  push    rsi
0x1800632bc  push    rdi
0x1800632bd  sub     rsp, 28h
0x1800632c1  mov     rbx, [rcx]
0x1800632c4  mov     rsi, rcx
0x1800632c7  cmp     rbx, rcx
0x1800632ca  jz      loc_1800633A8
0x1800632d0  cmp     byte ptr [rbx+3Ch], 0
0x1800632d4  mov     rbp, [rbx]
0x1800632d7  jnz     loc_18006339C
0x1800632dd  mov     rcx, rbx
0x1800632e0  call    RemoveDeviceAssociations
0x1800632e5  lea     rdi, [rbx+20h]
0x1800632e9  mov     rcx, [rdi]
0x1800632ec  cmp     rcx, rdi
0x1800632ef  jz      short loc_18006332D
0x1800632f1  cmp     [rcx+8], rdi
0x1800632f5  jnz     loc_1800633B2
0x1800632fb  mov     rax, [rcx]
0x1800632fe  cmp     [rax+8], rcx
0x180063302  jnz     loc_1800633B2
0x180063308  mov     [rdi], rax
0x18006330b  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x180063312  mov     [rax+8], rdi
0x180063316  xor     edx, edx; PriorityBoost
0x180063318  mov     dword ptr [rcx+30h], 0C0000034h
0x18006331f  call    cs:__imp_IofCompleteRequest
0x180063326  nop     dword ptr [rax+rax+00h]
0x18006332b  jmp     short loc_1800632E9
0x18006332d  cmp     qword ptr [rbx+30h], 0
0x180063332  jnz     short loc_18006339C
0x180063334  mov     rcx, [rbx+60h]; P
0x180063338  test    rcx, rcx
0x18006333b  jz      short loc_180063353
0x18006333d  xor     edx, edx; Tag
0x18006333f  call    cs:__imp_ExFreePoolWithTag
0x180063346  nop     dword ptr [rax+rax+00h]
0x18006334b  mov     qword ptr [rbx+60h], 0
0x180063353  mov     rcx, [rbx+68h]; P
0x180063357  test    rcx, rcx
0x18006335a  jz      short loc_180063372
0x18006335c  xor     edx, edx; Tag
0x18006335e  call    cs:__imp_ExFreePoolWithTag
0x180063365  nop     dword ptr [rax+rax+00h]
0x18006336a  mov     qword ptr [rbx+68h], 0
0x180063372  mov     rax, [rbx]
0x180063375  cmp     [rax+8], rbx
0x180063379  jnz     short loc_1800633B2
0x18006337b  mov     rcx, [rbx+8]
0x18006337f  cmp     [rcx], rbx
0x180063382  jnz     short loc_1800633B2
0x180063384  mov     [rcx], rax
0x180063387  xor     edx, edx; Tag
0x180063389  mov     [rax+8], rcx
0x18006338d  mov     rcx, rbx; P
0x180063390  call    cs:__imp_ExFreePoolWithTag
0x180063397  nop     dword ptr [rax+rax+00h]
0x18006339c  mov     rbx, rbp
0x18006339f  cmp     rbp, rsi
0x1800633a2  jnz     loc_1800632D0
0x1800633a8  add     rsp, 28h
0x1800633ac  pop     rdi
0x1800633ad  pop     rsi
0x1800633ae  pop     rbp
0x1800633af  pop     rbx
0x1800633b0  retn
0x1800633b2  mov     ecx, 3
0x1800633b7  int     29h; Win8: RtlFailFast(ecx)
```
