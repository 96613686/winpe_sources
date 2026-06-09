# DrDrive::Remove(void)

- ea: `0x140015bc0`
- end: `0x140015c3b`
- name: `?Remove@DrDrive@@UEAAXXZ`
- size: `123`
- prototype: `void __fastcall(DrDrive *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x1400027b0`
- `0x140003188`
- `0x14000327c`
- `0x140015bc0`

## pseudocode

```c
void __fastcall DrDrive::Remove(DrDrive *this)
{
  _DWORD *v2; // rax

  v2 = operator new(4u, 0x40u);
  if ( v2 )
  {
    *v2 = *((_DWORD *)this + 10);
    RDPDYN_DispatchNewDevMgmtEvent(v2, *(_DWORD *)(*((_QWORD *)this + 4) + 1128LL), 3u, 0);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, 4);
  }
  *((_DWORD *)this + 14) = 1;
}

```

## disassembly

```asm
0x140015bc0  push    rbx
0x140015bc2  sub     rsp, 20h
0x140015bc6  mov     edx, 40h ; '@'; unsigned __int64
0x140015bcb  mov     rbx, rcx
0x140015bce  lea     ecx, [rdx-3Ch]; unsigned __int64
0x140015bd1  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140015bd6  test    rax, rax
0x140015bd9  jz      short loc_140015BFB
0x140015bdb  mov     edx, [rbx+28h]
0x140015bde  xor     r9d, r9d; struct DrDevice *
0x140015be1  mov     [rax], edx
0x140015be3  mov     rcx, rax; void *
0x140015be6  mov     rdx, [rbx+20h]
0x140015bea  lea     r8d, [r9+3]; unsigned int
0x140015bee  mov     edx, [rdx+468h]; unsigned int
0x140015bf4  call    RDPDYN_DispatchNewDevMgmtEvent
0x140015bf9  jmp     short loc_140015C2D
0x140015bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140015c02  lea     rax, WPP_GLOBAL_Control
0x140015c09  cmp     rcx, rax
0x140015c0c  jz      short loc_140015C2D
0x140015c0e  cmp     byte ptr [rcx+29h], 2
0x140015c12  jb      short loc_140015C2D
0x140015c14  mov     rcx, [rcx+18h]
0x140015c18  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140015c1f  mov     edx, 10h
0x140015c24  lea     r9d, [rdx-0Ch]
0x140015c28  call    WPP_SF_d
0x140015c2d  mov     dword ptr [rbx+38h], 1
0x140015c34  add     rsp, 20h
0x140015c38  pop     rbx
0x140015c39  retn
```
