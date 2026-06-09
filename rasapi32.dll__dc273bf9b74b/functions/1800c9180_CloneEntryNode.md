# CloneEntryNode

- ea: `0x1800c9180`
- end: `0x1800c92bb`
- name: `CloneEntryNode`
- size: `315`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180096d00`

## callees

- `0x1800087f0`
- `0x18000ada0`
- `0x18000b0f4`
- `0x18004e984`
- `0x1800c9180`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c9237`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800c9237`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c9203`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c9203`
- `RPCRT4!UuidCreate` at `0x1800c9253`
- `RPCRT4!UuidCreate` at `0x1800c9253`

## pseudocode

```c
__int64 __fastcall CloneEntryNode(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rdi
  UUID *v6; // rax
  RPC_STATUS v7; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_38cda081c674317ed40163d707084d83_Traceguids);
  }
  v2 = 0;
  v3 = DuplicateEntryNode(a1);
  v4 = v3;
  if ( v3 )
  {
    v5 = *(_QWORD *)(v3 + 16);
    if ( v5 )
    {
      *(_DWORD *)(v5 + 252) = 0;
      *(_DWORD *)(v5 + 456) = GetTickCount();
      if ( *(_DWORD *)(v5 + 24) != 1 )
      {
        *(_DWORD *)(v5 + 124) = 0;
        *(_DWORD *)(v5 + 40) = 0;
      }
      Free0(*(_QWORD *)(v5 + 464));
      v6 = (UUID *)GlobalAlloc(0x40u, 0x10u);
      *(_QWORD *)(v5 + 464) = v6;
      if ( !v6 )
      {
        v2 = -2147024882;
        goto LABEL_15;
      }
      v7 = UuidCreate(v6);
      if ( !v7 || v7 == 1824 )
      {
        *(_DWORD *)(v5 + 532) = 0;
        goto LABEL_15;
      }
    }
  }
  v2 = -2147467259;
LABEL_15:
  if ( v2 && v4 )
  {
    DestroyEntryNode(v4);
    v4 = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_38cda081c674317ed40163d707084d83_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x1800c9180  push    rbx
0x1800c9182  push    rsi
0x1800c9183  push    rdi
0x1800c9184  push    r15
0x1800c9186  sub     rsp, 38h
0x1800c918a  mov     rdi, rcx
0x1800c918d  lea     r15, WPP_GLOBAL_Control
0x1800c9194  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c919b  cmp     rcx, r15
0x1800c919e  jz      short loc_1800C91C1
0x1800c91a0  test    byte ptr [rcx+1Ch], 80h
0x1800c91a4  jz      short loc_1800C91C1
0x1800c91a6  cmp     byte ptr [rcx+19h], 6
0x1800c91aa  jb      short loc_1800C91C1
0x1800c91ac  mov     edx, 0Fh
0x1800c91b1  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x1800c91b8  mov     rcx, [rcx+10h]
0x1800c91bc  call    WPP_SF_
0x1800c91c1  mov     [rsp+58h+var_30], 0
0x1800c91ca  xor     ebx, ebx
0x1800c91cc  mov     [rsp+58h+var_38], ebx
0x1800c91d0  mov     rcx, rdi
0x1800c91d3  call    DuplicateEntryNode
0x1800c91d8  mov     rsi, rax
0x1800c91db  mov     [rsp+58h+var_30], rax
0x1800c91e0  test    rax, rax
0x1800c91e3  jnz     short loc_1800C91F0
0x1800c91e5  mov     ebx, 80004005h
0x1800c91ea  mov     [rsp+58h+var_38], ebx
0x1800c91ee  jmp     short loc_1800C926E
0x1800c91f0  mov     rdi, [rax+10h]
0x1800c91f4  test    rdi, rdi
0x1800c91f7  jz      short loc_1800C91E5
0x1800c91f9  mov     dword ptr [rdi+0FCh], 0
0x1800c9203  call    cs:__imp_GetTickCount
0x1800c9209  mov     [rdi+1C8h], eax
0x1800c920f  cmp     dword ptr [rdi+18h], 1
0x1800c9213  jz      short loc_1800C9223
0x1800c9215  mov     dword ptr [rdi+7Ch], 0
0x1800c921c  mov     dword ptr [rdi+28h], 0
0x1800c9223  mov     rcx, [rdi+1D0h]
0x1800c922a  call    Free0
0x1800c922f  mov     edx, 10h; dwBytes
0x1800c9234  lea     ecx, [rdx+30h]; uFlags
0x1800c9237  call    cs:__imp_GlobalAlloc
0x1800c923d  mov     [rdi+1D0h], rax
0x1800c9244  test    rax, rax
0x1800c9247  jnz     short loc_1800C9250
0x1800c9249  mov     ebx, 8007000Eh
0x1800c924e  jmp     short loc_1800C91EA
0x1800c9250  mov     rcx, rax; Uuid
0x1800c9253  call    cs:__imp_UuidCreate
0x1800c9259  test    eax, eax
0x1800c925b  jz      short loc_1800C9264
0x1800c925d  cmp     eax, 720h
0x1800c9262  jnz     short loc_1800C91E5
0x1800c9264  mov     dword ptr [rdi+214h], 0
0x1800c926e  test    ebx, ebx
0x1800c9270  jz      short loc_1800C9281
0x1800c9272  test    rsi, rsi
0x1800c9275  jz      short loc_1800C9281
0x1800c9277  mov     rcx, rsi
0x1800c927a  call    DestroyEntryNode
0x1800c927f  xor     esi, esi
0x1800c9281  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9288  cmp     rcx, r15
0x1800c928b  jz      short loc_1800C92AE
0x1800c928d  test    byte ptr [rcx+1Ch], 80h
0x1800c9291  jz      short loc_1800C92AE
0x1800c9293  cmp     byte ptr [rcx+19h], 6
0x1800c9297  jb      short loc_1800C92AE
0x1800c9299  mov     edx, 10h
0x1800c929e  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x1800c92a5  mov     rcx, [rcx+10h]
0x1800c92a9  call    WPP_SF_
0x1800c92ae  mov     rax, rsi
0x1800c92b1  add     rsp, 38h
0x1800c92b5  pop     r15
0x1800c92b7  pop     rdi
0x1800c92b8  pop     rsi
0x1800c92b9  pop     rbx
0x1800c92ba  retn
0x1800df2df  push    rbp
0x1800df2e1  sub     rsp, 20h
0x1800df2e5  mov     rbp, rdx
0x1800df2e8  cmp     dword ptr [rbp+20h], 0
0x1800df2ec  jz      short loc_1800DF304
0x1800df2ee  mov     rcx, [rbp+28h]
0x1800df2f2  test    rcx, rcx
0x1800df2f5  jz      short loc_1800DF304
0x1800df2f7  call    DestroyEntryNode
0x1800df2fc  mov     qword ptr [rbp+28h], 0
0x1800df304  add     rsp, 20h
0x1800df308  pop     rbp
0x1800df309  retn
```
