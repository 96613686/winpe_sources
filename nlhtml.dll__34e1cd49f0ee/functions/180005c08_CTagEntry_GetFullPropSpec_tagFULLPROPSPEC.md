# CTagEntry::GetFullPropSpec(tagFULLPROPSPEC &)

- ea: `0x180005c08`
- end: `0x180005c34`
- name: `?GetFullPropSpec@CTagEntry@@QEAAXAEAUtagFULLPROPSPEC@@@Z`
- size: `44`
- prototype: `void __fastcall(CTagEntry *__hidden this, struct tagFULLPROPSPEC *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180005230`
- `0x1800053a0`
- `0x180005470`
- `0x180005dc0`

## callees

- `0x180005c08`

## pseudocode

```c
void __fastcall CTagEntry::GetFullPropSpec(CTagEntry *this, struct tagFULLPROPSPEC *a2)
{
  GUID *v2; // rax

  v2 = (GUID *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    a2->guidPropSet = *v2;
    a2->psProperty.ulKind = *((_DWORD *)this + 8);
    if ( *((_DWORD *)this + 8) )
      a2->psProperty.propid = *((_DWORD *)this + 12);
    else
      a2->psProperty.lpwstr = (LPOLESTR)*((_QWORD *)this + 8);
  }
}

```

## disassembly

```asm
0x180005c08  mov     rax, [rcx+28h]
0x180005c0c  test    rax, rax
0x180005c0f  jz      short locret_180005C2C
0x180005c11  movups  xmm0, xmmword ptr [rax]
0x180005c14  movdqu  xmmword ptr [rdx], xmm0
0x180005c18  mov     eax, [rcx+20h]
0x180005c1b  mov     [rdx+10h], eax
0x180005c1e  cmp     dword ptr [rcx+20h], 0
0x180005c22  jnz     short loc_180005C2D
0x180005c24  mov     rax, [rcx+40h]
0x180005c28  mov     [rdx+18h], rax
0x180005c2c  retn
0x180005c2d  mov     eax, [rcx+30h]
0x180005c30  mov     [rdx+18h], eax
0x180005c33  retn
```
