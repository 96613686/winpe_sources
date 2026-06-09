# CLogInfo::CLogInfo(CComponentData *,CLogSet *,EVENTLOGTYPE,int,int)

- ea: `0x1800165b0`
- end: `0x180016736`
- name: `??0CLogInfo@@QEAA@PEAVCComponentData@@PEAVCLogSet@@W4EVENTLOGTYPE@@HH@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007bd8`
- `0x180015f90`
- `0x180016084`

## callees

- `0x1800165b0`
- `0x180020430`

## pseudocode

```c
__int64 __fastcall CLogInfo::CLogInfo(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, int a6)
{
  wchar_t *v7; // rax
  _WORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // ecx
  __int64 result; // rax

  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)(a1 + 24) = 0;
  *(_QWORD *)a1 = &CLogInfo::`vftable';
  *(_DWORD *)(a1 + 28) = a4;
  *(_QWORD *)(a1 + 2648) = &CFilter::`vftable';
  *(_WORD *)(a1 + 2660) = 0;
  *(_WORD *)(a1 + 3702) = 0;
  *(_WORD *)(a1 + 4222) = 0;
  *(_QWORD *)(a1 + 4752) = 0;
  *(_DWORD *)(a1 + 2656) = 31;
  *(_QWORD *)(a1 + 4744) = 0;
  *(_DWORD *)(a1 + 3180) = 0;
  *(_DWORD *)(a1 + 4760) = 1;
  if ( a5 && g_wszAuxMessageSource )
  {
    v7 = &g_wszAuxMessageSource;
  }
  else
  {
    v7 = (wchar_t *)&String;
    if ( !a6 )
      v7 = (wchar_t *)(a1 + 32);
  }
  *(_QWORD *)(a1 + 4784) = 0;
  *(_QWORD *)(a1 + 4792) = v7;
  v8 = (_WORD *)(a1 + 554);
  *(_QWORD *)(a1 + 4800) = v8;
  *(_QWORD *)(a1 + 4808) = 0;
  *(_QWORD *)(a1 + 4816) = 0;
  *(_QWORD *)(a1 + 4824) = 0;
  *(_QWORD *)(a1 + 4832) = 0;
  *(_QWORD *)(a1 + 4840) = 0;
  *(_QWORD *)(a1 + 4848) = 0;
  *(_QWORD *)(a1 + 4856) = 0;
  *(_QWORD *)(a1 + 4864) = a3;
  *(_QWORD *)(a1 + 4872) = a2;
  if ( a5 )
    *(_WORD *)(a1 + 24) |= 1u;
  if ( a6 )
    *(_WORD *)(a1 + 24) |= 0x10u;
  *(_WORD *)(a1 + 32) = 0;
  *v8 = 0;
  *(_WORD *)(a1 + 1076) = 0;
  *(_WORD *)(a1 + 1598) = 0;
  *(_WORD *)(a1 + 4764) = 0;
  *(_WORD *)(a1 + 2120) = 0;
  if ( !CLogInfo::_wszType )
    LoadStr(0xD7u, &CLogInfo::_wszType, 0x14u, 0);
  v9 = *(_QWORD *)(a1 + 4872);
  v10 = *(_DWORD *)(v9 + 1144);
  *(_DWORD *)(v9 + 1144) = v10 + 1;
  result = a1;
  *(_DWORD *)(a1 + 4880) = v10;
  return result;
}

```

## disassembly

```asm
0x1800165b0  mov     [rsp+arg_0], rbx
0x1800165b5  push    rdi
0x1800165b6  sub     rsp, 20h
0x1800165ba  xor     edi, edi
0x1800165bc  lea     rax, ??_7CLogInfo@@6B@; const CLogInfo::`vftable'
0x1800165c3  mov     [rcx+8], rdi
0x1800165c7  mov     r10, r8
0x1800165ca  mov     r8d, [rsp+28h+arg_20]
0x1800165cf  mov     r11, rdx
0x1800165d2  mov     edx, [rsp+28h+arg_28]
0x1800165d6  mov     rbx, rcx
0x1800165d9  mov     [rcx+10h], rdi
0x1800165dd  mov     [rcx+18h], di
0x1800165e1  mov     [rcx], rax
0x1800165e4  lea     rax, ??_7CFilter@@6B@; const CFilter::`vftable'
0x1800165eb  mov     [rcx+1Ch], r9d
0x1800165ef  lea     r9d, [rdi+1]
0x1800165f3  mov     [rcx+0A58h], rax
0x1800165fa  mov     [rcx+0A64h], di
0x180016601  mov     [rcx+0E76h], di
0x180016608  mov     [rcx+107Eh], di
0x18001660f  mov     [rcx+1290h], rdi
0x180016616  mov     dword ptr [rcx+0A60h], 1Fh
0x180016620  mov     [rcx+1288h], rdi
0x180016627  mov     [rcx+0C6Ch], edi
0x18001662d  mov     [rcx+1298h], r9d
0x180016634  test    r8d, r8d
0x180016637  jz      short loc_18001664B
0x180016639  cmp     cs:?g_wszAuxMessageSource@@3PAGA, di; ushort near * g_wszAuxMessageSource
0x180016640  jz      short loc_18001664B
0x180016642  lea     rax, ?g_wszAuxMessageSource@@3PAGA; ushort near * g_wszAuxMessageSource
0x180016649  jmp     short loc_18001665A
0x18001664b  lea     rax, String
0x180016652  test    edx, edx
0x180016654  jnz     short loc_18001665A
0x180016656  lea     rax, [rcx+20h]
0x18001665a  mov     [rcx+12B0h], rdi
0x180016661  mov     [rcx+12B8h], rax
0x180016668  add     rcx, 22Ah
0x18001666f  mov     [rbx+12C0h], rcx
0x180016676  mov     [rbx+12C8h], rdi
0x18001667d  mov     [rbx+12D0h], rdi
0x180016684  mov     [rbx+12D8h], rdi
0x18001668b  mov     [rbx+12E0h], rdi
0x180016692  mov     [rbx+12E8h], rdi
0x180016699  mov     [rbx+12F0h], rdi
0x1800166a0  mov     [rbx+12F8h], rdi
0x1800166a7  mov     [rbx+1300h], r10
0x1800166ae  mov     [rbx+1308h], r11
0x1800166b5  test    r8d, r8d
0x1800166b8  jz      short loc_1800166BF
0x1800166ba  or      [rbx+18h], r9w
0x1800166bf  test    edx, edx
0x1800166c1  jz      short loc_1800166C8
0x1800166c3  or      word ptr [rbx+18h], 10h
0x1800166c8  mov     [rbx+20h], di
0x1800166cc  mov     [rcx], di
0x1800166cf  mov     [rbx+434h], di
0x1800166d6  mov     [rbx+63Eh], di
0x1800166dd  mov     [rbx+129Ch], di
0x1800166e4  mov     [rbx+848h], di
0x1800166eb  cmp     cs:?_wszType@CLogInfo@@0PAGA, di; ushort near * CLogInfo::_wszType
0x1800166f2  jnz     short loc_18001670C
0x1800166f4  xor     r9d, r9d; Source
0x1800166f7  lea     rdx, ?_wszType@CLogInfo@@0PAGA; Destination
0x1800166fe  mov     ecx, 0D7h; uID
0x180016703  lea     r8d, [r9+14h]; SizeInWords
0x180016707  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x18001670c  mov     rdx, [rbx+1308h]
0x180016713  mov     ecx, [rdx+478h]
0x180016719  lea     eax, [rcx+1]
0x18001671c  mov     [rdx+478h], eax
0x180016722  mov     rax, rbx
0x180016725  mov     [rbx+1310h], ecx
0x18001672b  mov     rbx, [rsp+28h+arg_0]
0x180016730  add     rsp, 20h
0x180016734  pop     rdi
0x180016735  retn
```
