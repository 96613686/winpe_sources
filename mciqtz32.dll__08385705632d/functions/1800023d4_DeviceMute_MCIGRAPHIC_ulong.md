# DeviceMute(_MCIGRAPHIC *,ulong)

- ea: `0x1800023d4`
- end: `0x18000243f`
- name: `?DeviceMute@@YAKPEAU_MCIGRAPHIC@@K@Z`
- size: `107`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005384`
- `0x180005634`

## callees

- `0x180001d48`
- `0x180001dfc`
- `0x180001e7c`
- `0x1800023d4`

## pseudocode

```c
__int64 __fastcall DeviceMute(struct _MCIGRAPHIC *a1, int a2)
{
  int v3; // eax
  int v4; // ecx

  v3 = -2147467259;
  if ( *((_QWORD *)a1 + 23) )
  {
    v4 = a2 & 0x4000;
    if ( (a2 & 0x200000) == 0 )
      *((_DWORD *)a1 + 58) = v4 != 0;
    if ( (a2 & 0x400000) == 0 )
      *((_DWORD *)a1 + 55) = v4 != 0;
    if ( !*((_DWORD *)a1 + 54) )
      ActuallyGetVolume(a1);
    v3 = ActuallySetVolume(a1);
  }
  return CheckResult(v3);
}

```

## disassembly

```asm
0x1800023d4  push    rbx
0x1800023d6  sub     rsp, 20h
0x1800023da  cmp     qword ptr [rcx+0B8h], 0
0x1800023e2  mov     rbx, rcx
0x1800023e5  mov     eax, 80004005h
0x1800023ea  jz      short loc_180002433
0x1800023ec  mov     ecx, edx
0x1800023ee  and     ecx, 4000h
0x1800023f4  bt      edx, 15h
0x1800023f8  jb      short loc_180002407
0x1800023fa  xor     eax, eax
0x1800023fc  test    ecx, ecx
0x1800023fe  setnz   al
0x180002401  mov     [rbx+0E8h], eax
0x180002407  bt      edx, 16h
0x18000240b  jb      short loc_18000241A
0x18000240d  xor     eax, eax
0x18000240f  test    ecx, ecx
0x180002411  setnz   al
0x180002414  mov     [rbx+0DCh], eax
0x18000241a  cmp     dword ptr [rbx+0D8h], 0
0x180002421  jnz     short loc_18000242B
0x180002423  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180002426  call    ?ActuallyGetVolume@@YAJPEAU_MCIGRAPHIC@@@Z; ActuallyGetVolume(_MCIGRAPHIC *)
0x18000242b  mov     rcx, rbx; struct _MCIGRAPHIC *
0x18000242e  call    ?ActuallySetVolume@@YAJPEAU_MCIGRAPHIC@@@Z; ActuallySetVolume(_MCIGRAPHIC *)
0x180002433  mov     ecx, eax; int
0x180002435  add     rsp, 20h
0x180002439  pop     rbx
0x18000243a  jmp     ?CheckResult@@YAKJ@Z; CheckResult(long)
```
