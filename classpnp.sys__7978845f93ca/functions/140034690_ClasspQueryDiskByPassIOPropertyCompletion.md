# ClasspQueryDiskByPassIOPropertyCompletion

- ea: `0x140034690`
- end: `0x1400347b4`
- name: `ClasspQueryDiskByPassIOPropertyCompletion`
- size: `292`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID Tag)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400134a0`
- `0x140027a24`
- `0x140034690`
- `0x14003e940`

## pseudocode

```c
__int64 __fastcall ClasspQueryDiskByPassIOPropertyCompletion(PDEVICE_OBJECT DeviceObject, _QWORD *Tag)
{
  _QWORD *DeviceExtension; // rbp
  _DWORD *v5; // rdi
  size_t v6; // r14
  int v7; // eax

  DeviceExtension = DeviceObject->DeviceExtension;
  v5 = (_DWORD *)Tag[3];
  v6 = *(unsigned int *)(Tag[23] + 8LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 153, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
  }
  v7 = *((_DWORD *)Tag + 12);
  if ( v7 == -1073741637 )
  {
    ClassReleaseRemoveLock(DeviceObject, Tag);
  }
  else
  {
    if ( v7 >= 0 && Tag[7] == 40 )
    {
      *(_QWORD *)(DeviceExtension[143] + 456LL) = *((_QWORD *)v5 + 1);
      *(_QWORD *)(DeviceExtension[143] + 464LL) = *((_QWORD *)v5 + 2);
      *(_QWORD *)(DeviceExtension[143] + 472LL) = *((_QWORD *)v5 + 3);
    }
    memset(v5, 0, v6);
    *v5 = 40;
    *((_QWORD *)v5 + 2) = ClassDereferenceBypassIODeviceObject;
    *((_QWORD *)v5 + 3) = ClassStartBypassIo;
    v5[1] = 40;
    *((_QWORD *)v5 + 1) = DeviceObject;
    *((_DWORD *)Tag + 12) = 0;
    Tag[7] = 40;
  }
  if ( *((_BYTE *)Tag + 65) )
    *(_BYTE *)(Tag[23] + 3LL) |= 1u;
  return 0;
}

```

## disassembly

```asm
0x140034690  push    rbx
0x140034692  push    rbp
0x140034693  push    rsi
0x140034694  push    rdi
0x140034695  push    r14
0x140034697  sub     rsp, 30h
0x14003469b  mov     rax, [rdx+0B8h]
0x1400346a2  mov     rbx, rdx
0x1400346a5  mov     rbp, [rcx+40h]
0x1400346a9  mov     rsi, rcx
0x1400346ac  mov     rdi, [rdx+18h]
0x1400346b0  mov     r14d, [rax+8]
0x1400346b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400346bb  lea     rax, WPP_GLOBAL_Control
0x1400346c2  cmp     rcx, rax
0x1400346c5  jz      short loc_1400346F6
0x1400346c7  mov     eax, [rcx+2Ch]
0x1400346ca  test    al, 10h
0x1400346cc  jz      short loc_1400346F6
0x1400346ce  cmp     byte ptr [rcx+29h], 4
0x1400346d2  jb      short loc_1400346F6
0x1400346d4  mov     rcx, [rcx+18h]
0x1400346d8  mov     edx, 99h
0x1400346dd  mov     [rsp+58h+var_30], r8
0x1400346e2  mov     r9, rsi
0x1400346e5  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400346ec  mov     [rsp+58h+var_38], rbx
0x1400346f1  call    WPP_SF_qqq
0x1400346f6  mov     eax, [rbx+30h]
0x1400346f9  cmp     eax, 0C00000BBh
0x1400346fe  jz      loc_14003478A
0x140034704  test    eax, eax
0x140034706  js      short loc_140034745
0x140034708  cmp     qword ptr [rbx+38h], 28h ; '('
0x14003470d  jnz     short loc_140034745
0x14003470f  mov     rcx, [rbp+478h]
0x140034716  mov     rax, [rdi+8]
0x14003471a  mov     [rcx+1C8h], rax
0x140034721  mov     rcx, [rbp+478h]
0x140034728  mov     rax, [rdi+10h]
0x14003472c  mov     [rcx+1D0h], rax
0x140034733  mov     rcx, [rbp+478h]
0x14003473a  mov     rax, [rdi+18h]
0x14003473e  mov     [rcx+1D8h], rax
0x140034745  mov     r8, r14; Size
0x140034748  xor     edx, edx; Val
0x14003474a  mov     rcx, rdi; void *
0x14003474d  call    memset
0x140034752  lea     rax, ClassDereferenceBypassIODeviceObject
0x140034759  mov     dword ptr [rdi], 28h ; '('
0x14003475f  mov     [rdi+10h], rax
0x140034763  lea     rax, ClassStartBypassIo
0x14003476a  mov     [rdi+18h], rax
0x14003476e  mov     dword ptr [rdi+4], 28h ; '('
0x140034775  mov     [rdi+8], rsi
0x140034779  mov     dword ptr [rbx+30h], 0
0x140034780  mov     qword ptr [rbx+38h], 28h ; '('
0x140034788  jmp     short loc_140034795
0x14003478a  mov     rdx, rbx; Tag
0x14003478d  mov     rcx, rsi; DeviceObject
0x140034790  call    ClassReleaseRemoveLock
0x140034795  cmp     byte ptr [rbx+41h], 0
0x140034799  jz      short loc_1400347A6
0x14003479b  mov     rax, [rbx+0B8h]
0x1400347a2  or      byte ptr [rax+3], 1
0x1400347a6  xor     eax, eax
0x1400347a8  add     rsp, 30h
0x1400347ac  pop     r14
0x1400347ae  pop     rdi
0x1400347af  pop     rsi
0x1400347b0  pop     rbp
0x1400347b1  pop     rbx
0x1400347b2  retn
```
