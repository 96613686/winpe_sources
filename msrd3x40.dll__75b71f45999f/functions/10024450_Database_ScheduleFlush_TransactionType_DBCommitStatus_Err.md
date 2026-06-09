# Database::ScheduleFlush(TransactionType,DBCommitStatus,Err &)

- ea: `0x10024450`
- end: `0x10024596`
- name: `?ScheduleFlush@Database@@IAEXW4TransactionType@@W4DBCommitStatus@@AAVErr@@@Z`
- size: `326`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10023830`
- `0x10024070`
- `0x100242b0`

## callees

- `0x10023bb0`
- `0x10024450`
- `0x1004f130`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100244a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100244a6`

## pseudocode

```c
void __thiscall Database::ScheduleFlush(int this, int a2, int a3, struct Err *a4)
{
  int v5; // eax
  int v6; // eax
  DWORD TickCount; // eax
  _DWORD *v8; // edx
  DWORD v9; // ebx
  int v10; // eax
  unsigned int v11; // esi
  DWORD v12; // ebx
  int v13; // eax
  DWORD v14; // ecx
  DWORD v15; // eax
  int v16; // [esp+10h] [ebp-1Ch] BYREF
  DWORD v17; // [esp+14h] [ebp-18h]
  int v18; // [esp+18h] [ebp-14h]

  if ( *(_DWORD *)(this + 384)
    && ((*(_BYTE *)(this + 20) & 0x10) == 0 || *(_DWORD *)(this + 964))
    && *(_DWORD *)(this + 72) )
  {
    v5 = *(_DWORD *)(this + 60);
    if ( a2 )
      v6 = *(_DWORD *)(v5 + 72);
    else
      v6 = *(_DWORD *)(v5 + 68);
    if ( v6 )
    {
      v18 = this;
      TickCount = GetTickCount();
      v8 = *(_DWORD **)(this + 60);
      v9 = TickCount;
      v10 = v8[21];
      if ( v10 )
      {
        if ( a3 == 1 || !*(_DWORD *)(this + 176) )
          *(_DWORD *)(this + 176) = v9 + v10;
        v11 = *(_DWORD *)(this + 180);
        if ( !v11 || v11 < v9 - 2 * v8[21] )
        {
          v12 = v8[21] + v9;
          v16 = 5;
          v17 = v12;
          System::Schedule((struct QMsg *)&Sys, (struct Err *)&v16, a4);
          if ( (*(_BYTE *)a4 & 8) == 0 )
          {
            *(_DWORD *)(this + 180) = v12;
            _InterlockedIncrement((volatile signed __int32 *)(this + 216));
          }
        }
      }
      else
      {
        if ( *(_DWORD *)(this + 100) == 2 )
          v13 = v8[20];
        else
          v13 = v8[19];
        v14 = *(_DWORD *)(this + 176);
        v15 = v9 + v13;
        v17 = v15;
        if ( !v14 || v15 < v14 )
        {
          *(_DWORD *)(this + 176) = v15;
          v16 = 2;
          System::Schedule((struct QMsg *)&Sys, (struct Err *)&v16, a4);
          if ( (*(_BYTE *)a4 & 8) == 0 )
            _InterlockedIncrement((volatile signed __int32 *)(this + 216));
        }
      }
    }
    else
    {
      Database::WriteDirtyPages((Database *)this, (void **)a4);
    }
  }
}

```

## disassembly

```asm
0x10024450  mov     edi, edi
0x10024452  push    ebp
0x10024453  mov     ebp, esp
0x10024455  sub     esp, 20h
0x10024458  push    ebx
0x10024459  push    esi
0x1002445a  push    edi
0x1002445b  mov     edi, ecx
0x1002445d  cmp     dword ptr [edi+180h], 0
0x10024464  jbe     loc_1002458D
0x1002446a  test    byte ptr [edi+14h], 10h
0x1002446e  jz      short loc_1002447D
0x10024470  cmp     dword ptr [edi+3C4h], 0
0x10024477  jz      loc_1002458D
0x1002447d  cmp     dword ptr [edi+48h], 0
0x10024481  jz      loc_1002458D
0x10024487  mov     eax, [ebp+arg_0]
0x1002448a  sub     eax, 0
0x1002448d  mov     eax, [edi+3Ch]
0x10024490  jz      short loc_10024497
0x10024492  mov     eax, [eax+48h]
0x10024495  jmp     short loc_1002449A
0x10024497  mov     eax, [eax+44h]
0x1002449a  sub     eax, 0
0x1002449d  jz      loc_10024585
0x100244a3  mov     [ebp+var_14], edi
0x100244a6  call    ds:__imp__GetTickCount@0; GetTickCount()
0x100244ac  mov     edx, [edi+3Ch]
0x100244af  mov     ebx, eax
0x100244b1  mov     eax, [edx+54h]
0x100244b4  test    eax, eax
0x100244b6  jz      short loc_10024524
0x100244b8  cmp     [ebp+arg_4], 1
0x100244bc  jz      short loc_100244C7
0x100244be  cmp     dword ptr [edi+0B0h], 0
0x100244c5  jnz     short loc_100244CF
0x100244c7  add     eax, ebx
0x100244c9  mov     [edi+0B0h], eax
0x100244cf  mov     esi, [edi+0B4h]
0x100244d5  test    esi, esi
0x100244d7  jz      short loc_100244EA
0x100244d9  mov     ecx, [edx+54h]
0x100244dc  mov     eax, ebx
0x100244de  add     ecx, ecx
0x100244e0  sub     eax, ecx
0x100244e2  cmp     esi, eax
0x100244e4  jnb     loc_1002458D
0x100244ea  mov     esi, [ebp+arg_8]
0x100244ed  lea     eax, [ebp+var_1C]
0x100244f0  add     ebx, [edx+54h]
0x100244f3  mov     ecx, offset ?Sys@@3VSystem@@A; lpParameter
0x100244f8  push    esi
0x100244f9  push    eax; struct Err *
0x100244fa  mov     [ebp+var_1C], 5
0x10024501  mov     [ebp+var_18], ebx
0x10024504  call    ?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z; System::Schedule(QMsg *,Err &)
0x10024509  test    byte ptr [esi], 8
0x1002450c  jnz     short loc_1002458D
0x1002450e  mov     [edi+0B4h], ebx
0x10024514  lock inc dword ptr [edi+0D8h]
0x1002451b  pop     edi
0x1002451c  pop     esi
0x1002451d  pop     ebx
0x1002451e  mov     esp, ebp
0x10024520  pop     ebp
0x10024521  retn    0Ch
0x10024524  mov     eax, [edi+64h]
0x10024527  sub     eax, 0
0x1002452a  jz      short loc_1002453B
0x1002452c  sub     eax, 1
0x1002452f  jz      short loc_1002453B
0x10024531  sub     eax, 1
0x10024534  jnz     short loc_1002453B
0x10024536  mov     eax, [edx+50h]
0x10024539  jmp     short loc_1002453E
0x1002453b  mov     eax, [edx+4Ch]
0x1002453e  mov     ecx, [edi+0B0h]
0x10024544  add     eax, ebx
0x10024546  mov     [ebp+var_18], eax
0x10024549  test    ecx, ecx
0x1002454b  jz      short loc_10024551
0x1002454d  cmp     eax, ecx
0x1002454f  jnb     short loc_1002458D
0x10024551  mov     esi, [ebp+arg_8]
0x10024554  mov     ecx, offset ?Sys@@3VSystem@@A; this
0x10024559  mov     [edi+0B0h], eax
0x1002455f  lea     eax, [ebp+var_1C]
0x10024562  push    esi
0x10024563  push    eax; struct Err *
0x10024564  mov     [ebp+var_1C], 2
0x1002456b  call    ?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z; System::Schedule(QMsg *,Err &)
0x10024570  test    byte ptr [esi], 8
0x10024573  jnz     short loc_1002458D
0x10024575  lock inc dword ptr [edi+0D8h]
0x1002457c  pop     edi
0x1002457d  pop     esi
0x1002457e  pop     ebx
0x1002457f  mov     esp, ebp
0x10024581  pop     ebp
0x10024582  retn    0Ch
0x10024585  push    [ebp+arg_8]; struct Err *
0x10024588  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@@Z; Database::WriteDirtyPages(Err &)
0x1002458d  pop     edi
0x1002458e  pop     esi
0x1002458f  pop     ebx
0x10024590  mov     esp, ebp
0x10024592  pop     ebp
0x10024593  retn    0Ch
```
