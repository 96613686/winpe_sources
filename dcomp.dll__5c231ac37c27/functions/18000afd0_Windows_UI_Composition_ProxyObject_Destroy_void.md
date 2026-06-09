# Windows::UI::Composition::ProxyObject::Destroy(void)

- ea: `0x18000afd0`
- end: `0x18000b1d4`
- name: `?Destroy@ProxyObject@Composition@UI@Windows@@MEAAXXZ`
- size: `516`
- prototype: `void __fastcall(Windows::UI::Composition::ProxyObject *__hidden this)`
- caller_count: `40`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180009a20`
- `0x18000af50`
- `0x18000c120`
- `0x180033b60`
- `0x1800454e0`
- `0x180046650`
- `0x180046770`
- `0x18005d9c0`
- `0x18006f0f0`
- `0x180094660`
- `0x1800a02e0`
- `0x1800aa550`
- `0x1800adde0`
- `0x1800af680`
- `0x1800b03c0`
- `0x1800b2eb0`
- `0x1800b4330`
- `0x1800bdf40`
- `0x1800c8f10`
- `0x1800ca820`
- `0x1800cb260`
- `0x1800d15b0`
- `0x1800d4900`
- `0x1800d67c0`
- `0x1800d9060`
- `0x1800da620`
- `0x18012fcc0`
- `0x1801346e0`
- `0x180146c60`
- `0x180158a10`
- `0x180159cc0`
- `0x18015a640`
- `0x18015aca0`
- `0x18015b4f0`
- `0x180160000`
- `0x1801653d0`
- `0x18016a880`
- `0x18016b910`
- `0x180171570`
- `0x180171720`

## callees

- `0x18000afd0`
- `0x18000b1e0`
- `0x18000bc00`
- `0x18000bf80`
- `0x18000c01c`
- `0x18001a494`
- `0x1800c7c30`
- `0x1800e77ac`
- `0x1800ebd74`
- `0x1800f6f34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000b199`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000b1c9`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000b199`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18000b1c9`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000b136`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000b183`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000b136`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000b183`
- `ntdll!RtlLookupElementGenericTable` at `0x18000b021`
- `ntdll!RtlLookupElementGenericTable` at `0x18000b0b7`
- `ntdll!RtlLookupElementGenericTable` at `0x18000b021`
- `ntdll!RtlLookupElementGenericTable` at `0x18000b0b7`

## pseudocode

```c
void __fastcall Windows::UI::Composition::ProxyObject::Destroy(Windows::UI::Composition::ProxyObject *this)
{
  __int64 v1; // rbx
  Windows::UI::Composition::ProxyObject *v2; // r13
  struct _RTL_GENERIC_TABLE *v3; // rdi
  int v4; // r15d
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  int *v7; // r14
  Windows::UI::Composition::AnimationBindingManager *v8; // rax
  unsigned __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _QWORD *v12; // rax
  __int64 *v13; // r12
  _QWORD *v14; // r13
  __int64 v15; // r15
  unsigned int v16; // edx
  _QWORD *v17; // rcx
  int Buffer; // [rsp+20h] [rbp-48h] BYREF
  __int64 v19; // [rsp+28h] [rbp-40h]
  _DWORD v20[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v21; // [rsp+38h] [rbp-30h]
  _DWORD v22[2]; // [rsp+48h] [rbp-20h] BYREF
  __int128 v23; // [rsp+50h] [rbp-18h]
  int v25; // [rsp+B8h] [rbp+50h]

  v1 = *((_QWORD *)this + 3);
  v2 = this;
  v3 = *(struct _RTL_GENERIC_TABLE **)(v1 + 816);
  if ( !v3 )
  {
    v8 = (Windows::UI::Composition::AnimationBindingManager *)DefaultHeap::AllocClear(0x130u);
    if ( v8 )
    {
      v10 = Windows::UI::Composition::AnimationBindingManager::AnimationBindingManager(v8);
      *(_QWORD *)(v1 + 816) = v10;
      v3 = (struct _RTL_GENERIC_TABLE *)v10;
      if ( v10 )
        goto LABEL_2;
    }
    else
    {
      *(_QWORD *)(v1 + 816) = 0;
    }
    Microsoft::WRL2::FailFast::OutOfMemory(v9);
  }
LABEL_2:
  v4 = *((_DWORD *)v2 + 36);
  v25 = v4;
  v19 = 0;
  Buffer = v4;
  v5 = RtlLookupElementGenericTable(v3 + 1, &Buffer);
  v6 = v5;
  if ( v5 )
  {
    v7 = (int *)v5[1];
    if ( !v7 )
LABEL_5:
      Microsoft::WRL2::FailFast::Unexpected(0);
LABEL_11:
    if ( v7 )
    {
      v11 = *v7;
      v20[0] = v4;
      v20[1] = v11;
      v21 = 0;
      v12 = RtlLookupElementGenericTable(v3, v20);
      v13 = v12 + 2;
      if ( !v12[1] && !*v13 )
        goto LABEL_5;
      v14 = v12;
      while ( 1 )
      {
        v15 = v14[1];
        if ( v15 )
        {
          v14[1] = *(_QWORD *)(v15 + 24);
        }
        else
        {
          v15 = *v13;
          if ( !*v13 )
          {
            v22[0] = *(_DWORD *)v14;
            v22[1] = *((_DWORD *)v14 + 1);
            v23 = 0;
            v2 = this;
            if ( !RtlDeleteElementGenericTable(v3, v22) )
              RaiseFailFastException(0, 0, 1u);
            v7 = (int *)*((_QWORD *)v7 + 1);
            v4 = v25;
            goto LABEL_11;
          }
          *v13 = *(_QWORD *)(v15 + 24);
        }
        Windows::UI::Composition::CompositionPropertyAnimator::RemoveTarget(*(Windows::UI::Composition::CompositionPropertyAnimator **)(v15 + 8));
        *(_QWORD *)(*(_QWORD *)(v15 + 8) + 176LL) = 0;
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock((void *)(v15 + 8));
        Windows::UI::Composition::ExpressionListEntry::`scalar deleting destructor'(
          (Windows::UI::Composition::ExpressionListEntry *)v15,
          v16);
      }
    }
    while ( 1 )
    {
      v17 = (_QWORD *)v6[1];
      if ( !v17 )
        break;
      v6[1] = v17[1];
      operator delete(v17, 0x10u);
    }
    v20[0] = *(_DWORD *)v6;
    *(_QWORD *)&v21 = 0;
    if ( !RtlDeleteElementGenericTable(v3 + 1, v20) )
      RaiseFailFastException(0, 0, 1u);
  }
  Windows::UI::Composition::CompositionObject::Destroy(v2);
}

```

## disassembly

```asm
0x18000afd0  mov     [rsp-40h+arg_0], rcx
0x18000afd5  push    rbp
0x18000afd6  push    rbx
0x18000afd7  push    rsi
0x18000afd8  push    rdi
0x18000afd9  push    r12
0x18000afdb  push    r13
0x18000afdd  push    r14
0x18000afdf  push    r15
0x18000afe1  mov     rbp, rsp
0x18000afe4  sub     rsp, 68h
0x18000afe8  mov     rbx, [rcx+18h]
0x18000afec  mov     r13, rcx
0x18000afef  mov     rdi, [rbx+330h]
0x18000aff6  test    rdi, rdi
0x18000aff9  jz      short loc_18000B058
0x18000affb  mov     r15d, [r13+90h]
0x18000b002  lea     rbx, [rdi+48h]
0x18000b006  mov     rcx, rbx; Table
0x18000b009  mov     [rbp+arg_8], r15d
0x18000b00d  lea     rdx, [rbp+Buffer]; Buffer
0x18000b011  mov     [rbp+var_40], 0
0x18000b019  mov     [rbp+Buffer], r15d
0x18000b01d  mov     [rbp+Table], rbx
0x18000b021  call    cs:__imp_RtlLookupElementGenericTable
0x18000b027  mov     rsi, rax
0x18000b02a  test    rax, rax
0x18000b02d  jnz     short loc_18000B047
0x18000b02f  mov     rcx, r13; this
0x18000b032  add     rsp, 68h
0x18000b036  pop     r15
0x18000b038  pop     r14
0x18000b03a  pop     r13
0x18000b03c  pop     r12
0x18000b03e  pop     rdi
0x18000b03f  pop     rsi
0x18000b040  pop     rbx
0x18000b041  pop     rbp
0x18000b042  jmp     ?Destroy@CompositionObject@Composition@UI@Windows@@MEAAXXZ; Windows::UI::Composition::CompositionObject::Destroy(void)
0x18000b047  mov     r14, [rax+8]
0x18000b04b  test    r14, r14
0x18000b04e  jnz     short loc_18000B095
0x18000b050  xor     ecx, ecx; char *
0x18000b052  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x18000b058  mov     ecx, 130h; unsigned __int64
0x18000b05d  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x18000b062  test    rax, rax
0x18000b065  jz      short loc_18000B084
0x18000b067  mov     rcx, rax; this
0x18000b06a  call    ??0AnimationBindingManager@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::AnimationBindingManager::AnimationBindingManager(void)
0x18000b06f  mov     [rbx+330h], rax
0x18000b076  mov     rdi, rax
0x18000b079  test    rax, rax
0x18000b07c  jnz     loc_18000AFFB
0x18000b082  jmp     short loc_18000B08F
0x18000b084  mov     qword ptr [rbx+330h], 0
0x18000b08f  call    ?OutOfMemory@FailFast@WRL2@Microsoft@@SAX_K@Z; Microsoft::WRL2::FailFast::OutOfMemory(unsigned __int64)
0x18000b095  test    r14, r14
0x18000b098  jz      loc_18000B151
0x18000b09e  mov     eax, [r14]
0x18000b0a1  lea     rdx, [rbp+var_38]; Buffer
0x18000b0a5  xorps   xmm0, xmm0
0x18000b0a8  mov     [rbp+var_38], r15d
0x18000b0ac  mov     rcx, rdi; Table
0x18000b0af  mov     [rbp+var_34], eax
0x18000b0b2  movdqu  [rbp+var_30], xmm0
0x18000b0b7  call    cs:__imp_RtlLookupElementGenericTable
0x18000b0bd  cmp     qword ptr [rax+8], 0
0x18000b0c2  lea     r12, [rax+10h]
0x18000b0c6  jz      loc_18000B1B1
0x18000b0cc  mov     r13, rax
0x18000b0cf  mov     r15, [r13+8]
0x18000b0d3  test    r15, r15
0x18000b0d6  jz      short loc_18000B10C
0x18000b0d8  mov     rax, [r15+18h]
0x18000b0dc  mov     [r13+8], rax
0x18000b0e0  lea     rbx, [r15+8]
0x18000b0e4  mov     rcx, [rbx]; this
0x18000b0e7  call    ?RemoveTarget@CompositionPropertyAnimator@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::CompositionPropertyAnimator::RemoveTarget(void)
0x18000b0ec  mov     rax, [rbx]
0x18000b0ef  mov     rcx, rbx; void *
0x18000b0f2  mov     qword ptr [rax+0B0h], 0
0x18000b0fd  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18000b102  mov     rcx, r15; this
0x18000b105  call    ??_GExpressionListEntry@Composition@UI@Windows@@QEAAPEAXI@Z; Windows::UI::Composition::ExpressionListEntry::`scalar deleting destructor'(uint)
0x18000b10a  jmp     short loc_18000B0CF
0x18000b10c  mov     r15, [r12]
0x18000b110  test    r15, r15
0x18000b113  jnz     loc_18000B1A4
0x18000b119  mov     eax, [r13+0]
0x18000b11d  lea     rdx, [rbp+var_20]; Buffer
0x18000b121  mov     [rbp+var_20], eax
0x18000b124  xorps   xmm0, xmm0
0x18000b127  mov     eax, [r13+4]
0x18000b12b  mov     rcx, rdi; Table
0x18000b12e  mov     [rbp+var_1C], eax
0x18000b131  movdqu  [rbp+var_18], xmm0
0x18000b136  call    cs:__imp_RtlDeleteElementGenericTable
0x18000b13c  mov     r13, [rbp+arg_0]
0x18000b140  test    al, al
0x18000b142  jz      short loc_18000B1C1
0x18000b144  mov     r14, [r14+8]
0x18000b148  mov     r15d, [rbp+arg_8]
0x18000b14c  jmp     loc_18000B095
0x18000b151  mov     rcx, [rsi+8]; void *
0x18000b155  test    rcx, rcx
0x18000b158  jz      short loc_18000B16E
0x18000b15a  mov     rax, [rcx+8]
0x18000b15e  mov     edx, 10h; unsigned __int64
0x18000b163  mov     [rsi+8], rax
0x18000b167  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b16c  jmp     short loc_18000B151
0x18000b16e  mov     eax, [rsi]
0x18000b170  lea     rdx, [rbp+var_38]; Buffer
0x18000b174  mov     rcx, [rbp+Table]; Table
0x18000b178  mov     [rbp+var_38], eax
0x18000b17b  mov     qword ptr [rbp+var_30], 0
0x18000b183  call    cs:__imp_RtlDeleteElementGenericTable
0x18000b189  test    al, al
0x18000b18b  jnz     loc_18000B02F
0x18000b191  xor     edx, edx; pContextRecord
0x18000b193  xor     ecx, ecx; pExceptionRecord
0x18000b195  lea     r8d, [rdx+1]; dwFlags
0x18000b199  call    cs:__imp_RaiseFailFastException
0x18000b19f  jmp     loc_18000B02F
0x18000b1a4  mov     rax, [r15+18h]
0x18000b1a8  mov     [r12], rax
0x18000b1ac  jmp     loc_18000B0E0
0x18000b1b1  cmp     qword ptr [r12], 0
0x18000b1b6  jz      loc_18000B050
0x18000b1bc  jmp     loc_18000B0CC
0x18000b1c1  xor     edx, edx; pContextRecord
0x18000b1c3  xor     ecx, ecx; pExceptionRecord
0x18000b1c5  lea     r8d, [rdx+1]; dwFlags
0x18000b1c9  call    cs:__imp_RaiseFailFastException
0x18000b1cf  jmp     loc_18000B144
```
