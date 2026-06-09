# ScmCmDeregisterSap

- ea: `0x140004160`
- end: `0x1400042d5`
- name: `ScmCmDeregisterSap`
- size: `373`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002bd8`
- `0x140004160`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041ac`
- `ntoskrnl!IofCompleteRequest` at `0x14000428d`
- `ntoskrnl!IofCompleteRequest` at `0x14000428d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400041d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000427c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400041d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000427c`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400041ee`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400041ee`

## pseudocode

```c
__int64 ScmCmDeregisterSap()
{
  KIRQL v0; // al
  KSPIN_LOCK *v1; // rcx
  KIRQL v2; // si
  unsigned int v3; // ebx
  PIRP v4; // rax
  IRP *v5; // rdi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  v0 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 55);
  v1 = (KSPIN_LOCK *)SstpGlobals;
  v2 = v0;
  if ( *((_DWORD *)SstpGlobals + 112) )
  {
    v4 = IoCsqRemoveNextIrp((PIO_CSQ)SstpGlobals + 1, 0);
    v5 = v4;
    if ( v4 )
    {
      v3 = 259;
      *((_DWORD *)SstpGlobals + 112) = 2;
      *(_DWORD *)v4->AssociatedIrp.MasterIrp = 2;
      v4->IoStatus.Status = 0;
      v4->IoStatus.Information = 8208;
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 55, v2);
      IofCompleteRequest(v5, 0);
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    }
    v1 = (KSPIN_LOCK *)SstpGlobals;
    v3 = -1073741670;
  }
  else
  {
    v3 = 0;
  }
  KeReleaseSpinLock(v1 + 55, v2);
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x140004160  push    rbx
0x140004162  push    rsi
0x140004163  push    rdi
0x140004164  push    r14
0x140004166  sub     rsp, 28h
0x14000416a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004171  lea     r14, WPP_GLOBAL_Control
0x140004178  cmp     rcx, r14
0x14000417b  jz      short loc_14000419E
0x14000417d  mov     eax, [rcx+2Ch]
0x140004180  and     eax, 82h
0x140004185  cmp     al, 82h
0x140004187  jnz     short loc_14000419E
0x140004189  mov     rcx, [rcx+18h]
0x14000418d  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140004194  mov     edx, 1Dh
0x140004199  call    WPP_SF_
0x14000419e  mov     rcx, cs:SstpGlobals
0x1400041a5  add     rcx, 1B8h; SpinLock
0x1400041ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400041b3  nop     dword ptr [rax+rax+00h]
0x1400041b8  mov     rcx, cs:SstpGlobals
0x1400041bf  mov     sil, al
0x1400041c2  cmp     dword ptr [rcx+1C0h], 0
0x1400041c9  jnz     short loc_1400041E8
0x1400041cb  xor     ebx, ebx
0x1400041cd  add     rcx, 1B8h; SpinLock
0x1400041d4  mov     dl, sil; NewIrql
0x1400041d7  call    cs:__imp_KeReleaseSpinLock
0x1400041de  nop     dword ptr [rax+rax+00h]
0x1400041e3  jmp     loc_140004299
0x1400041e8  add     rcx, 40h ; '@'; Csq
0x1400041ec  xor     edx, edx; PeekContext
0x1400041ee  call    cs:__imp_IoCsqRemoveNextIrp
0x1400041f5  nop     dword ptr [rax+rax+00h]
0x1400041fa  mov     rdi, rax
0x1400041fd  test    rax, rax
0x140004200  jnz     short loc_14000423C
0x140004202  mov     rcx, cs:WPP_GLOBAL_Control
0x140004209  cmp     rcx, r14
0x14000420c  jz      short loc_14000422E
0x14000420e  mov     eax, [rcx+2Ch]
0x140004211  test    al, 2
0x140004213  jz      short loc_14000422E
0x140004215  cmp     byte ptr [rcx+29h], 1
0x140004219  jb      short loc_14000422E
0x14000421b  mov     rcx, [rcx+18h]
0x14000421f  lea     edx, [rdi+1Eh]
0x140004222  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140004229  call    WPP_SF_
0x14000422e  mov     rcx, cs:SstpGlobals
0x140004235  mov     ebx, 0C000009Ah
0x14000423a  jmp     short loc_1400041CD
0x14000423c  mov     rax, cs:SstpGlobals
0x140004243  mov     dl, sil; NewIrql
0x140004246  mov     ebx, 103h
0x14000424b  mov     dword ptr [rax+1C0h], 2
0x140004255  mov     rax, [rdi+18h]
0x140004259  mov     dword ptr [rax], 2
0x14000425f  mov     dword ptr [rdi+30h], 0
0x140004266  mov     qword ptr [rdi+38h], 2010h
0x14000426e  mov     rcx, cs:SstpGlobals
0x140004275  add     rcx, 1B8h; SpinLock
0x14000427c  call    cs:__imp_KeReleaseSpinLock
0x140004283  nop     dword ptr [rax+rax+00h]
0x140004288  xor     edx, edx; PriorityBoost
0x14000428a  mov     rcx, rdi; Irp
0x14000428d  call    cs:__imp_IofCompleteRequest
0x140004294  nop     dword ptr [rax+rax+00h]
0x140004299  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042a0  cmp     rcx, r14
0x1400042a3  jz      short loc_1400042C8
0x1400042a5  mov     edx, [rcx+2Ch]
0x1400042a8  and     edx, 82h
0x1400042ae  cmp     dl, 82h
0x1400042b1  jnz     short loc_1400042C8
0x1400042b3  mov     rcx, [rcx+18h]
0x1400042b7  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x1400042be  mov     edx, 1Fh
0x1400042c3  call    WPP_SF_
0x1400042c8  mov     eax, ebx
0x1400042ca  add     rsp, 28h
0x1400042ce  pop     r14
0x1400042d0  pop     rdi
0x1400042d1  pop     rsi
0x1400042d2  pop     rbx
0x1400042d3  retn
```
