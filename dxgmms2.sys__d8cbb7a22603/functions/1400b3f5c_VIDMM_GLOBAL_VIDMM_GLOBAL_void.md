# VIDMM_GLOBAL::VIDMM_GLOBAL(void)

- ea: `0x1400b3f5c`
- end: `0x1400b451b`
- name: `??0VIDMM_GLOBAL@@QEAA@XZ`
- size: `1471`
- prototype: `VIDMM_GLOBAL *__fastcall(VIDMM_GLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400c2a08`

## callees

- `0x140058cac`
- `0x140059380`
- `0x1400b3f5c`
- `0x1400b9a28`
- `0x1400c7380`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400b44aa`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400b44aa`
- `ntoskrnl!KeInitializeEvent` at `0x1400b4218`
- `ntoskrnl!KeInitializeEvent` at `0x1400b4291`
- `ntoskrnl!KeInitializeEvent` at `0x1400b4218`
- `ntoskrnl!KeInitializeEvent` at `0x1400b4291`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b41c7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b424f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b4471`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b41c7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b424f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400b4471`

## pseudocode

```c
VIDMM_GLOBAL *__fastcall VIDMM_GLOBAL::VIDMM_GLOBAL(VIDMM_GLOBAL *this)
{
  __int64 v2; // rdx
  char *v3; // rcx
  __int64 v4; // rax

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_BYTE *)this + 12) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_DWORD *)this + 178) = 0;
  *((_DWORD *)this + 179) = 13;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_BYTE *)this + 736) = 0;
  memset((char *)this + 737, 0, 0x40u);
  memset((char *)this + 2600, 0, 0x200u);
  *((_DWORD *)this + 779) = 0;
  *((_QWORD *)this + 390) = 0;
  *((_QWORD *)this + 391) = 0;
  *((_BYTE *)this + 3200) = 0;
  *((_BYTE *)this + 3202) = 0;
  *((_QWORD *)this + 501) = 0;
  *((_DWORD *)this + 1004) = 0;
  *((_QWORD *)this + 4505) = 0;
  *((_QWORD *)this + 4506) = 0;
  *((_DWORD *)this + 9014) = 0;
  *((_DWORD *)this + 9015) = 78;
  *((_DWORD *)this + 9016) = 71;
  *((_QWORD *)this + 4510) = (char *)this + 36072;
  *((_QWORD *)this + 4509) = (char *)this + 36072;
  *((_QWORD *)this + 4512) = (char *)this + 36088;
  *((_QWORD *)this + 4511) = (char *)this + 36088;
  *((_QWORD *)this + 4517) = 0;
  *((_QWORD *)this + 4518) = 0;
  *((_DWORD *)this + 9038) = 0;
  *((_DWORD *)this + 9039) = 1;
  *((_DWORD *)this + 9040) = -1;
  *((_DWORD *)this + 9062) = 0;
  *((_DWORD *)this + 9064) = 257;
  *((_BYTE *)this + 36260) = 0;
  *((_QWORD *)this + 4535) = 0;
  *((_QWORD *)this + 4536) = 0;
  *((_DWORD *)this + 9074) = 0;
  *((_DWORD *)this + 9075) = 12;
  *((_BYTE *)this + 36304) = 0;
  *((_QWORD *)this + 4539) = 0;
  *((_QWORD *)this + 4540) = 0;
  *((_QWORD *)this + 4551) = 0;
  *((_QWORD *)this + 4552) = 0;
  *((_DWORD *)this + 9106) = 0;
  *((_DWORD *)this + 9107) = 78;
  *((_DWORD *)this + 9108) = 46;
  *((_DWORD *)this + 9110) = -1;
  *((_QWORD *)this + 4556) = 0;
  *((_QWORD *)this + 4557) = 0;
  *((_QWORD *)this + 4558) = 0;
  *((_QWORD *)this + 4559) = 0;
  memset((char *)this + 36672, 0, 0x220u);
  *((_BYTE *)this + 37224) &= 0x9Du;
  *((_BYTE *)this + 37225) &= 0xF2u;
  *((_BYTE *)this + 37227) &= ~1u;
  *((_DWORD *)this + 9304) = 0;
  *((_WORD *)this + 18614) = 0;
  *((_BYTE *)this + 37233) = 0;
  *((_QWORD *)this + 4663) = 0;
  *((_QWORD *)this + 4664) = 0;
  *((_DWORD *)this + 9330) = 0;
  *((_DWORD *)this + 9331) = 1;
  DXGK_LOG::DXGK_LOG((VIDMM_GLOBAL *)((char *)this + 37328));
  *((_QWORD *)this + 4670) = 0;
  *((_DWORD *)this + 9342) = 0;
  *((_QWORD *)this + 4672) = 0;
  *((_QWORD *)this + 4673) = 0;
  *((_DWORD *)this + 9348) = 0;
  *((_DWORD *)this + 9349) = 22;
  *((_DWORD *)this + 9350) = 66;
  *((_QWORD *)this + 4677) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 4676);
  *((_QWORD *)this + 4680) = 0;
  *((_QWORD *)this + 4681) = 0;
  *((_DWORD *)this + 9364) = 0;
  *((_DWORD *)this + 9365) = 1;
  *((_DWORD *)this + 9370) = 0;
  *((_DWORD *)this + 9386) = 1;
  *((_QWORD *)this + 4684) = (char *)this + 37464;
  *((_QWORD *)this + 4683) = (char *)this + 37464;
  *((_QWORD *)this + 4691) = DXG_DEFERRED_WORK_QUEUE::DeferredWorkQueueCallback;
  *((_QWORD *)this + 4692) = (char *)this + 37440;
  *((_QWORD *)this + 4689) = 0;
  KeInitializeEvent((PRKEVENT)this + 1562, NotificationEvent, 1u);
  VIDMM_PURGE_TELEMETRY::VIDMM_PURGE_TELEMETRY((VIDMM_GLOBAL *)((char *)this + 37552), this);
  *((_DWORD *)this + 10178) = 0;
  *((_QWORD *)this + 5106) = (char *)this + 40840;
  *((_QWORD *)this + 5105) = (char *)this + 40840;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 5125);
  *((_QWORD *)this + 5126) = 0;
  *((_QWORD *)this + 5127) = 0;
  *((_QWORD *)this + 5128) = 0;
  *((_DWORD *)this + 10258) = 0;
  *((_DWORD *)this + 10259) = 1;
  *((_DWORD *)this + 10266) = 0;
  KeInitializeEvent((PRKEVENT)this + 1710, NotificationEvent, 1u);
  *((_QWORD *)this + 5135) = 0;
  *((_QWORD *)this + 5136) = 0;
  *((_QWORD *)this + 5137) = 0;
  *((_QWORD *)this + 5138) = 0;
  *((_QWORD *)this + 5139) = 0;
  *((_QWORD *)this + 5140) = 0;
  *((_QWORD *)this + 5141) = 0;
  *((_DWORD *)this + 10284) = 0;
  *((_DWORD *)this + 10285) = 1;
  *((_DWORD *)this + 10286) = -1;
  *((_QWORD *)this + 5144) = 0;
  *((_QWORD *)this + 5145) = 0;
  *((_DWORD *)this + 10292) = 0;
  *((_DWORD *)this + 10293) = 7;
  *((_DWORD *)this + 10294) = 60;
  *((_QWORD *)this + 5158) = 0;
  *((_QWORD *)this + 5159) = 0;
  *((_QWORD *)this + 5160) = 0;
  *((_QWORD *)this + 5161) = 0;
  *((_QWORD *)this + 5162) = 0;
  *((_BYTE *)this + 41304) = 0;
  *((_QWORD *)this + 5164) = 0;
  *((_QWORD *)this + 5165) = 0;
  *((_DWORD *)this + 10332) = 0;
  *((_DWORD *)this + 10333) = 78;
  *((_DWORD *)this + 10334) = -1;
  *((_BYTE *)this + 41344) = 0;
  *((_DWORD *)this + 10337) = -1;
  *((_BYTE *)this + 41368) = 0;
  *((_QWORD *)this + 5172) = 0;
  *((_QWORD *)this + 5173) = 0;
  *((_QWORD *)this + 5176) = 0;
  *((_QWORD *)this + 5177) = 0;
  *((_DWORD *)this + 10380) = 0;
  v2 = 0;
  *((_QWORD *)this + 5199) = 0;
  *((_QWORD *)this + 82) = (char *)this + 648;
  *((_QWORD *)this + 81) = (char *)this + 648;
  *((_QWORD *)this + 5088) = (char *)this + 40696;
  *((_QWORD *)this + 5087) = (char *)this + 40696;
  *((_QWORD *)this + 4679) = (char *)this + 37424;
  *((_QWORD *)this + 4678) = (char *)this + 37424;
  *((_QWORD *)this + 84) = (char *)this + 664;
  *((_QWORD *)this + 83) = (char *)this + 664;
  *((_QWORD *)this + 86) = (char *)this + 680;
  *((_QWORD *)this + 85) = (char *)this + 680;
  *((_QWORD *)this + 4516) = (char *)this + 36120;
  *((_QWORD *)this + 4515) = (char *)this + 36120;
  *((_QWORD *)this + 4514) = (char *)this + 36104;
  *((_QWORD *)this + 4513) = (char *)this + 36104;
  *((_QWORD *)this + 5157) = (char *)this + 41248;
  *((_QWORD *)this + 5156) = (char *)this + 41248;
  *((_QWORD *)this + 5170) = (char *)this + 41352;
  *((_QWORD *)this + 5169) = (char *)this + 41352;
  *((_QWORD *)this + 4534) = (char *)this + 36264;
  *((_QWORD *)this + 4533) = (char *)this + 36264;
  do
  {
    v3 = (char *)this + 16 * v2 + 41184;
    *((_QWORD *)this + 2 * v2 + 5149) = v3;
    v4 = 2 * (v2 + 2574);
    ++v2;
    *((_QWORD *)this + v4) = v3;
  }
  while ( v2 != 4 );
  *((_QWORD *)this + 401) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)this + 5086);
  *((_DWORD *)this + 778) = 1;
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 36544), 0, 0, 0, 0x20u, 0x61356956u, 0);
  *((_QWORD *)this + 5174) = 0;
  *((_QWORD *)this + 5112) = VidMmUpgrade64KBWork;
  *((_QWORD *)this + 5113) = this;
  *((_QWORD *)this + 5110) = 0;
  *((_QWORD *)this + 5114) = 2;
  *((_DWORD *)this + 10206) = 0x40000;
  InitializePeriodicTrimData((VIDMM_GLOBAL *)((char *)this + 36328));
  InitializePeriodicTrimData((VIDMM_GLOBAL *)((char *)this + 36368));
  return this;
}

```

## disassembly

```asm
0x1400b3f5c  mov     [rsp+arg_0], rbx
0x1400b3f61  mov     [rsp+arg_8], r14
0x1400b3f66  push    r15
0x1400b3f68  sub     rsp, 40h
0x1400b3f6c  xor     r14d, r14d
0x1400b3f6f  mov     rbx, rcx
0x1400b3f72  mov     [rcx], r14
0x1400b3f75  xor     edx, edx; Val
0x1400b3f77  mov     [rcx+8], r14d
0x1400b3f7b  mov     [rcx+0Ch], r14b
0x1400b3f7f  mov     [rcx+10h], r14
0x1400b3f83  lea     r8d, [r14+40h]; Size
0x1400b3f87  mov     [rcx+28h], r14d
0x1400b3f8b  mov     [rcx+38h], r14
0x1400b3f8f  mov     [rcx+2B8h], r14
0x1400b3f96  mov     [rcx+2C0h], r14
0x1400b3f9d  mov     [rcx+2C8h], r14d
0x1400b3fa4  mov     dword ptr [rcx+2CCh], 0Dh
0x1400b3fae  mov     [rcx+2D0h], r14
0x1400b3fb5  mov     [rcx+2D8h], r14
0x1400b3fbc  mov     [rcx+2E0h], r14b
0x1400b3fc3  add     rcx, 2E1h; void *
0x1400b3fca  call    memset
0x1400b3fcf  lea     rcx, [rbx+0A28h]; void *
0x1400b3fd6  xor     edx, edx; Val
0x1400b3fd8  mov     r8d, 200h; Size
0x1400b3fde  call    memset
0x1400b3fe3  mov     [rbx+0C2Ch], r14d
0x1400b3fea  lea     rax, [rbx+8CE8h]
0x1400b3ff1  mov     [rbx+0C30h], r14
0x1400b3ff8  lea     r15d, [r14+1]
0x1400b3ffc  mov     [rbx+0C38h], r14
0x1400b4003  lea     rcx, [rbx+8F40h]; void *
0x1400b400a  mov     [rbx+0C80h], r14b
0x1400b4011  xor     edx, edx; Val
0x1400b4013  mov     [rbx+0C82h], r14b
0x1400b401a  mov     r8d, 220h; Size
0x1400b4020  mov     [rbx+0FA8h], r14
0x1400b4027  mov     [rbx+0FB0h], r14d
0x1400b402e  mov     [rbx+8CC8h], r14
0x1400b4035  mov     [rbx+8CD0h], r14
0x1400b403c  mov     [rbx+8CD8h], r14d
0x1400b4043  mov     dword ptr [rbx+8CDCh], 4Eh ; 'N'
0x1400b404d  mov     dword ptr [rbx+8CE0h], 47h ; 'G'
0x1400b4057  mov     [rax+8], rax
0x1400b405b  mov     [rax], rax
0x1400b405e  lea     rax, [rbx+8CF8h]
0x1400b4065  mov     [rax+8], rax
0x1400b4069  mov     [rax], rax
0x1400b406c  mov     [rbx+8D28h], r14
0x1400b4073  mov     [rbx+8D30h], r14
0x1400b407a  mov     [rbx+8D38h], r14d
0x1400b4081  mov     [rbx+8D3Ch], r15d
0x1400b4088  mov     dword ptr [rbx+8D40h], 0FFFFFFFFh
0x1400b4092  mov     [rbx+8D98h], r14d
0x1400b4099  mov     dword ptr [rbx+8DA0h], 101h
0x1400b40a3  mov     [rbx+8DA4h], r14b
0x1400b40aa  mov     [rbx+8DB8h], r14
0x1400b40b1  mov     [rbx+8DC0h], r14
0x1400b40b8  mov     [rbx+8DC8h], r14d
0x1400b40bf  mov     dword ptr [rbx+8DCCh], 0Ch
0x1400b40c9  mov     [rbx+8DD0h], r14b
0x1400b40d0  mov     [rbx+8DD8h], r14
0x1400b40d7  mov     [rbx+8DE0h], r14
0x1400b40de  mov     [rbx+8E38h], r14
0x1400b40e5  mov     [rbx+8E40h], r14
0x1400b40ec  mov     [rbx+8E48h], r14d
0x1400b40f3  mov     dword ptr [rbx+8E4Ch], 4Eh ; 'N'
0x1400b40fd  mov     dword ptr [rbx+8E50h], 2Eh ; '.'
0x1400b4107  mov     dword ptr [rbx+8E58h], 0FFFFFFFFh
0x1400b4111  mov     [rbx+8E60h], r14
0x1400b4118  mov     [rbx+8E68h], r14
0x1400b411f  mov     [rbx+8E70h], r14
0x1400b4126  mov     [rbx+8E78h], r14
0x1400b412d  call    memset
0x1400b4132  and     byte ptr [rbx+9168h], 9Dh
0x1400b4139  and     byte ptr [rbx+9169h], 0F2h
0x1400b4140  and     byte ptr [rbx+916Bh], 0FEh
0x1400b4147  mov     [rbx+9160h], r14d
0x1400b414e  mov     [rbx+916Ch], r14w
0x1400b4156  mov     [rbx+9171h], r14b
0x1400b415d  mov     [rbx+91B8h], r14
0x1400b4164  mov     [rbx+91C0h], r14
0x1400b416b  mov     [rbx+91C8h], r14d
0x1400b4172  mov     [rbx+91CCh], r15d
0x1400b4179  lea     rcx, [rbx+91D0h]; this
0x1400b4180  call    ??0DXGK_LOG@@QEAA@XZ; DXGK_LOG::DXGK_LOG(void)
0x1400b4185  mov     [rbx+91F0h], r14
0x1400b418c  lea     rcx, [rbx+9220h]; SpinLock
0x1400b4193  mov     [rbx+91F8h], r14d
0x1400b419a  mov     [rbx+9200h], r14
0x1400b41a1  mov     [rbx+9208h], r14
0x1400b41a8  mov     [rbx+9210h], r14d
0x1400b41af  mov     dword ptr [rbx+9214h], 16h
0x1400b41b9  mov     dword ptr [rbx+9218h], 42h ; 'B'
0x1400b41c3  mov     [rcx+8], r14
0x1400b41c7  call    cs:__imp_KeInitializeSpinLock
0x1400b41ce  nop     dword ptr [rax+rax+00h]
0x1400b41d3  lea     rcx, [rbx+9240h]
0x1400b41da  mov     r8b, r15b; State
0x1400b41dd  mov     [rcx], r14
0x1400b41e0  lea     rax, [rcx+18h]
0x1400b41e4  mov     [rcx+8], r14
0x1400b41e8  xor     edx, edx; Type
0x1400b41ea  mov     [rcx+10h], r14d
0x1400b41ee  mov     [rcx+14h], r15d
0x1400b41f2  mov     [rcx+28h], r14d
0x1400b41f6  mov     [rcx+68h], r15d
0x1400b41fa  mov     [rax+8], rax
0x1400b41fe  mov     [rax], rax
0x1400b4201  lea     rax, ?DeferredWorkQueueCallback@DXG_DEFERRED_WORK_QUEUE@@SAXPEAX@Z; DXG_DEFERRED_WORK_QUEUE::DeferredWorkQueueCallback(void *)
0x1400b4208  mov     [rcx+58h], rax
0x1400b420c  mov     [rcx+60h], rcx
0x1400b4210  mov     [rcx+48h], r14
0x1400b4214  add     rcx, 30h ; '0'; Event
0x1400b4218  call    cs:__imp_KeInitializeEvent
0x1400b421f  nop     dword ptr [rax+rax+00h]
0x1400b4224  lea     rcx, [rbx+92B0h]; this
0x1400b422b  mov     rdx, rbx; struct VIDMM_GLOBAL *
0x1400b422e  call    ??0VIDMM_PURGE_TELEMETRY@@QEAA@PEAVVIDMM_GLOBAL@@@Z; VIDMM_PURGE_TELEMETRY::VIDMM_PURGE_TELEMETRY(VIDMM_GLOBAL *)
0x1400b4233  lea     rax, [rbx+9F88h]
0x1400b423a  mov     [rbx+9F08h], r14d
0x1400b4241  lea     rcx, [rbx+0A028h]; SpinLock
0x1400b4248  mov     [rax+8], rax
0x1400b424c  mov     [rax], rax
0x1400b424f  call    cs:__imp_KeInitializeSpinLock
0x1400b4256  nop     dword ptr [rax+rax+00h]
0x1400b425b  mov     [rbx+0A030h], r14
0x1400b4262  lea     rcx, [rbx+0A050h]; Event
0x1400b4269  mov     [rbx+0A038h], r14
0x1400b4270  mov     r8b, r15b; State
0x1400b4273  mov     [rbx+0A040h], r14
0x1400b427a  xor     edx, edx; Type
0x1400b427c  mov     [rbx+0A048h], r14d
0x1400b4283  mov     [rbx+0A04Ch], r15d
0x1400b428a  mov     [rbx+0A068h], r14d
0x1400b4291  call    cs:__imp_KeInitializeEvent
0x1400b4298  nop     dword ptr [rax+rax+00h]
0x1400b429d  mov     [rbx+0A078h], r14
0x1400b42a4  mov     [rbx+0A080h], r14
0x1400b42ab  mov     [rbx+0A088h], r14
0x1400b42b2  mov     [rbx+0A090h], r14
0x1400b42b9  mov     [rbx+0A098h], r14
0x1400b42c0  mov     [rbx+0A0A0h], r14
0x1400b42c7  mov     [rbx+0A0A8h], r14
0x1400b42ce  mov     [rbx+0A0B0h], r14d
0x1400b42d5  mov     [rbx+0A0B4h], r15d
0x1400b42dc  mov     dword ptr [rbx+0A0B8h], 0FFFFFFFFh
0x1400b42e6  mov     [rbx+0A0C0h], r14
0x1400b42ed  mov     [rbx+0A0C8h], r14
0x1400b42f4  mov     [rbx+0A0D0h], r14d
0x1400b42fb  mov     dword ptr [rbx+0A0D4h], 7
0x1400b4305  mov     dword ptr [rbx+0A0D8h], 3Ch ; '<'
0x1400b430f  mov     [rbx+0A130h], r14
0x1400b4316  mov     [rbx+0A138h], r14
0x1400b431d  mov     [rbx+0A140h], r14
0x1400b4324  mov     [rbx+0A148h], r14
0x1400b432b  mov     [rbx+0A150h], r14
0x1400b4332  mov     [rbx+0A158h], r14b
0x1400b4339  mov     [rbx+0A160h], r14
0x1400b4340  mov     [rbx+0A168h], r14
0x1400b4347  mov     [rbx+0A170h], r14d
0x1400b434e  mov     dword ptr [rbx+0A174h], 4Eh ; 'N'
0x1400b4358  mov     dword ptr [rbx+0A178h], 0FFFFFFFFh
0x1400b4362  mov     [rbx+0A180h], r14b
0x1400b4369  mov     dword ptr [rbx+0A184h], 0FFFFFFFFh
0x1400b4373  mov     [rbx+0A198h], r14b
0x1400b437a  mov     [rbx+0A1A0h], r14
0x1400b4381  mov     [rbx+0A1A8h], r14
0x1400b4388  mov     [rbx+0A1C0h], r14
0x1400b438f  mov     [rbx+0A1C8h], r14
0x1400b4396  lea     rax, [rbx+288h]
0x1400b439d  mov     [rbx+0A230h], r14d
0x1400b43a4  mov     edx, r14d
0x1400b43a7  mov     [rbx+0A278h], r14
0x1400b43ae  mov     [rax+8], rax
0x1400b43b2  mov     [rax], rax
0x1400b43b5  lea     rax, [rbx+9EF8h]
0x1400b43bc  mov     [rax+8], rax
0x1400b43c0  mov     [rax], rax
0x1400b43c3  lea     rax, [rbx+9230h]
0x1400b43ca  mov     [rax+8], rax
0x1400b43ce  mov     [rax], rax
0x1400b43d1  lea     rax, [rbx+298h]
0x1400b43d8  mov     [rax+8], rax
0x1400b43dc  mov     [rax], rax
0x1400b43df  lea     rax, [rbx+2A8h]
0x1400b43e6  mov     [rax+8], rax
0x1400b43ea  mov     [rax], rax
0x1400b43ed  lea     rax, [rbx+8D18h]
0x1400b43f4  mov     [rax+8], rax
0x1400b43f8  mov     [rax], rax
0x1400b43fb  lea     rax, [rbx+8D08h]
0x1400b4402  mov     [rax+8], rax
0x1400b4406  mov     [rax], rax
0x1400b4409  lea     rax, [rbx+0A120h]
0x1400b4410  mov     [rax+8], rax
0x1400b4414  mov     [rax], rax
0x1400b4417  lea     rax, [rbx+0A188h]
0x1400b441e  mov     [rax+8], rax
0x1400b4422  mov     [rax], rax
0x1400b4425  lea     rax, [rbx+8DA8h]
0x1400b442c  mov     [rax+8], rax
0x1400b4430  mov     [rax], rax
0x1400b4433  mov     rax, rdx
0x1400b4436  lea     rcx, [rbx+0A0E0h]
0x1400b443d  shl     rax, 4
0x1400b4441  add     rcx, rax
0x1400b4444  mov     [rax+rbx+0A0E8h], rcx
0x1400b444c  lea     rax, [rdx+0A0Eh]
0x1400b4453  add     rax, rax
0x1400b4456  add     rdx, r15
0x1400b4459  mov     [rbx+rax*8], rcx
0x1400b445d  cmp     rdx, 4
0x1400b4461  jnz     short loc_1400B4433
0x1400b4463  lea     rcx, [rbx+9EF0h]; SpinLock
0x1400b446a  mov     [rbx+0C88h], r14
0x1400b4471  call    cs:__imp_KeInitializeSpinLock
0x1400b4478  nop     dword ptr [rax+rax+00h]
0x1400b447d  mov     [rsp+48h+Depth], r14w; Depth
0x1400b4483  lea     rcx, [rbx+8EC0h]; Lookaside
0x1400b448a  mov     [rsp+48h+Tag], 61356956h; Tag
0x1400b4492  xor     r9d, r9d; Flags
0x1400b4495  xor     r8d, r8d; Free
0x1400b4498  mov     [rsp+48h+Size], 20h ; ' '; Size
0x1400b44a1  xor     edx, edx; Allocate
0x1400b44a3  mov     [rbx+0C28h], r15d
0x1400b44aa  call    cs:__imp_ExInitializePagedLookasideList
0x1400b44b1  nop     dword ptr [rax+rax+00h]
0x1400b44b6  mov     [rbx+0A1B0h], r14
0x1400b44bd  lea     rax, ?VidMmUpgrade64KBWork@@YAXPEAX@Z; VidMmUpgrade64KBWork(void *)
0x1400b44c4  mov     [rbx+9FC0h], rax
0x1400b44cb  lea     rcx, [rbx+8DE8h]; struct VIDMM_PERIODIC_TRIM_DATA *
0x1400b44d2  mov     [rbx+9FC8h], rbx
0x1400b44d9  mov     [rbx+9FB0h], r14
0x1400b44e0  mov     qword ptr [rbx+9FD0h], 2
0x1400b44eb  mov     dword ptr [rbx+9F78h], 40000h
0x1400b44f5  call    ?InitializePeriodicTrimData@@YAXPEAUVIDMM_PERIODIC_TRIM_DATA@@@Z; InitializePeriodicTrimData(VIDMM_PERIODIC_TRIM_DATA *)
0x1400b44fa  lea     rcx, [rbx+8E10h]; struct VIDMM_PERIODIC_TRIM_DATA *
0x1400b4501  call    ?InitializePeriodicTrimData@@YAXPEAUVIDMM_PERIODIC_TRIM_DATA@@@Z; InitializePeriodicTrimData(VIDMM_PERIODIC_TRIM_DATA *)
0x1400b4506  mov     r14, [rsp+48h+arg_8]
0x1400b450b  mov     rax, rbx
0x1400b450e  mov     rbx, [rsp+48h+arg_0]
0x1400b4513  add     rsp, 40h
0x1400b4517  pop     r15
0x1400b4519  retn
```
