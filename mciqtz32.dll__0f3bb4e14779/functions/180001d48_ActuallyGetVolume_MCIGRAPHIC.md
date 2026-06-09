# ActuallyGetVolume(_MCIGRAPHIC *)

- ea: `0x180001d48`
- end: `0x180001df5`
- name: `?ActuallyGetVolume@@YAJPEAU_MCIGRAPHIC@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023d4`
- `0x180005934`

## callees

- `0x180001d48`
- `0x180007010`

## import_xrefs

- `QUARTZ!DBToAmpFactor` at `0x180001dcf`
- `QUARTZ!DBToAmpFactor` at `0x180001de1`
- `QUARTZ!DBToAmpFactor` at `0x180001dcf`
- `QUARTZ!DBToAmpFactor` at `0x180001de1`

## pseudocode

```c
__int64 __fastcall ActuallyGetVolume(struct _MCIGRAPHIC *a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // ecx
  int v5; // eax
  __int64 v6; // rcx
  int v8; // [rsp+30h] [rbp+8h] BYREF
  int v9; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  v2 = *((_QWORD *)a1 + 23);
  v9 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v2 + 64LL))(v2, &v8) >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)a1 + 23) + 80LL))(*((_QWORD *)a1 + 23), &v9);
    v4 = v8;
    *((_DWORD *)a1 + 57) = v8;
    *((_DWORD *)a1 + 60) = v4;
    *((_DWORD *)a1 + 54) = 1;
    if ( v3 >= 0 )
    {
      if ( v9 <= 0 )
      {
        if ( v9 < 0 )
          *((_DWORD *)a1 + 60) = v4 + v9;
      }
      else
      {
        *((_DWORD *)a1 + 57) = v4 - v9;
      }
    }
    v5 = ((__int64 (*)(void))DBToAmpFactor)();
    v6 = *((unsigned int *)a1 + 60);
    *((_DWORD *)a1 + 56) = v5;
    *((_DWORD *)a1 + 59) = DBToAmpFactor(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180001d48  push    rbx
0x180001d4a  sub     rsp, 20h
0x180001d4e  mov     rbx, rcx
0x180001d51  mov     [rsp+28h+arg_0], 0
0x180001d59  mov     rcx, [rcx+0B8h]
0x180001d60  lea     rdx, [rsp+28h+arg_0]
0x180001d65  mov     [rsp+28h+arg_8], 0
0x180001d6d  mov     rax, [rcx]
0x180001d70  mov     rax, [rax+40h]
0x180001d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d79  test    eax, eax
0x180001d7b  js      short loc_180001DED
0x180001d7d  mov     rcx, [rbx+0B8h]
0x180001d84  lea     rdx, [rsp+28h+arg_8]
0x180001d89  mov     rax, [rcx]
0x180001d8c  mov     rax, [rax+50h]
0x180001d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d95  mov     ecx, [rsp+28h+arg_0]
0x180001d99  mov     [rbx+0E4h], ecx
0x180001d9f  mov     [rbx+0F0h], ecx
0x180001da5  mov     dword ptr [rbx+0D8h], 1
0x180001daf  test    eax, eax
0x180001db1  js      short loc_180001DCF
0x180001db3  mov     eax, [rsp+28h+arg_8]
0x180001db7  test    eax, eax
0x180001db9  jle     short loc_180001DC5
0x180001dbb  sub     ecx, eax
0x180001dbd  mov     [rbx+0E4h], ecx
0x180001dc3  jmp     short loc_180001DCF
0x180001dc5  jns     short loc_180001DCF
0x180001dc7  add     eax, ecx
0x180001dc9  mov     [rbx+0F0h], eax
0x180001dcf  call    cs:__imp_DBToAmpFactor
0x180001dd5  mov     ecx, [rbx+0F0h]
0x180001ddb  mov     [rbx+0E0h], eax
0x180001de1  call    cs:__imp_DBToAmpFactor
0x180001de7  mov     [rbx+0ECh], eax
0x180001ded  xor     eax, eax
0x180001def  add     rsp, 20h
0x180001df3  pop     rbx
0x180001df4  retn
```
