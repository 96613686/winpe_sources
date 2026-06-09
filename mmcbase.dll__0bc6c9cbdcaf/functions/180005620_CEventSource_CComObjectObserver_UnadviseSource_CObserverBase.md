# _CEventSource<CComObjectObserver>::UnadviseSource(CObserverBase &)

- ea: `0x180005620`
- end: `0x180005665`
- name: `?UnadviseSource@?$_CEventSource@VCComObjectObserver@@@@UEAAXAEAVCObserverBase@@@Z`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005620`
- `0x18000566c`

## pseudocode

```c
void __fastcall _CEventSource<CComObjectObserver>::UnadviseSource(__int64 a1, __int64 a2)
{
  __int64 **v2; // r8
  __int64 *i; // rax

  if ( a1 )
    ++*(_DWORD *)(a1 + 24);
  v2 = *(__int64 ***)(a1 + 8);
  for ( i = *v2; i != (__int64 *)v2; i = (__int64 *)*i )
  {
    if ( !*((_BYTE *)i + 24) && i[2] == a2 )
    {
      *((_BYTE *)i + 24) = 1;
      i[2] = 0;
      break;
    }
  }
  if ( (*(_DWORD *)(a1 + 24))-- == 1 )
    _CEventSource<CComObjectObserver>::CleanupDeleted(a1);
}

```

## disassembly

```asm
0x180005620  sub     rsp, 28h
0x180005624  test    rcx, rcx
0x180005627  jz      short loc_18000562C
0x180005629  inc     dword ptr [rcx+18h]
0x18000562c  mov     r8, [rcx+8]
0x180005630  mov     rax, [r8]
0x180005633  cmp     rax, r8
0x180005636  jz      short loc_180005650
0x180005638  cmp     byte ptr [rax+18h], 0
0x18000563c  jnz     short loc_180005660
0x18000563e  cmp     [rax+10h], rdx
0x180005642  jnz     short loc_180005660
0x180005644  mov     byte ptr [rax+18h], 1
0x180005648  mov     qword ptr [rax+10h], 0
0x180005650  sub     dword ptr [rcx+18h], 1
0x180005654  jnz     short loc_18000565B
0x180005656  call    ?CleanupDeleted@?$_CEventSource@VCComObjectObserver@@@@AEAAXXZ; _CEventSource<CComObjectObserver>::CleanupDeleted(void)
0x18000565b  add     rsp, 28h
0x18000565f  retn
0x180005660  mov     rax, [rax]
0x180005663  jmp     short loc_180005633
```
