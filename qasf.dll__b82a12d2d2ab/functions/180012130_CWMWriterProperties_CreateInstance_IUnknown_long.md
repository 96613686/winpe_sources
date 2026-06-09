# CWMWriterProperties::CreateInstance(IUnknown *,long *)

- ea: `0x180012130`
- end: `0x1800121da`
- name: `?CreateInstance@CWMWriterProperties@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `170`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001020`
- `0x180012130`

## pseudocode

```c
struct CUnknown *__fastcall CWMWriterProperties::CreateInstance(struct IUnknown *a1, int *a2)
{
  struct IUnknown *v4; // rax
  struct IUnknown *v5; // r8
  struct CUnknown *result; // rax

  v4 = (struct IUnknown *)operator new(0x78u);
  if ( v4 )
  {
    _InterlockedIncrement(&CBaseObject::m_cObjects);
    v5 = v4 + 1;
    if ( a1 )
      v5 = a1;
    v4[2].lpVtbl = (struct IUnknownVtbl *)v5;
    LODWORD(v4[3].lpVtbl) = 0;
    v4->lpVtbl = (struct IUnknownVtbl *)&CWMWriterProperties::`vftable'{for `IPropertyPage'};
    v4[1].lpVtbl = (struct IUnknownVtbl *)&CWMWriterProperties::`vftable'{for `CUnknown'};
    v4[4].lpVtbl = 0;
    v4[5].lpVtbl = 0;
    v4[6].lpVtbl = 0;
    LODWORD(v4[7].lpVtbl) = 0;
    HIDWORD(v4[7].lpVtbl) = 101;
    v4[8].lpVtbl = (struct IUnknownVtbl *)100;
    v4[9].lpVtbl = 0;
    v4[10].lpVtbl = 0;
    v4[11].lpVtbl = 0;
    v4[12].lpVtbl = 0;
    v4[13].lpVtbl = 0;
    v4[14].lpVtbl = 0;
  }
  else
  {
    v4 = 0;
  }
  result = (struct CUnknown *)((unsigned __int64)&v4[1] & -(__int64)(v4 != 0));
  if ( !result )
    *a2 = -2147024882;
  return result;
}

```

## disassembly

```asm
0x180012130  mov     [rsp+arg_0], rbx
0x180012135  push    rdi
0x180012136  sub     rsp, 20h
0x18001213a  mov     rdi, rcx
0x18001213d  mov     rbx, rdx
0x180012140  mov     ecx, 78h ; 'x'; Size
0x180012145  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001214a  xor     edx, edx
0x18001214c  test    rax, rax
0x18001214f  jz      short loc_1800121B7
0x180012151  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180012158  lea     rcx, ??_7CWMWriterProperties@@6BIPropertyPage@@@; const CWMWriterProperties::`vftable'{for `IPropertyPage'}
0x18001215f  test    rdi, rdi
0x180012162  lea     r8, [rax+8]
0x180012166  cmovnz  r8, rdi
0x18001216a  mov     [rax+10h], r8
0x18001216e  mov     [rax+18h], edx
0x180012171  mov     [rax], rcx
0x180012174  lea     rcx, ??_7CWMWriterProperties@@6BCUnknown@@@; const CWMWriterProperties::`vftable'{for `CUnknown'}
0x18001217b  mov     [rax+8], rcx
0x18001217f  mov     [rax+20h], rdx
0x180012183  mov     [rax+28h], rdx
0x180012187  mov     [rax+30h], rdx
0x18001218b  mov     [rax+38h], edx
0x18001218e  mov     dword ptr [rax+3Ch], 65h ; 'e'
0x180012195  mov     qword ptr [rax+40h], 64h ; 'd'
0x18001219d  mov     [rax+48h], rdx
0x1800121a1  mov     [rax+50h], rdx
0x1800121a5  mov     [rax+58h], rdx
0x1800121a9  mov     [rax+60h], rdx
0x1800121ad  mov     [rax+68h], rdx
0x1800121b1  mov     [rax+70h], rdx
0x1800121b5  jmp     short loc_1800121BA
0x1800121b7  mov     rax, rdx
0x1800121ba  lea     rcx, [rax+8]
0x1800121be  neg     rax
0x1800121c1  sbb     rax, rax
0x1800121c4  and     rax, rcx
0x1800121c7  jnz     short loc_1800121CF
0x1800121c9  mov     dword ptr [rbx], 8007000Eh
0x1800121cf  mov     rbx, [rsp+28h+arg_0]
0x1800121d4  add     rsp, 20h
0x1800121d8  pop     rdi
0x1800121d9  retn
```
